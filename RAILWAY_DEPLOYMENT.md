# Railway Deployment Checklist

## Overview

Two separate Railway projects required:

| Project | Repo | Type | Purpose |
|---------|------|------|---------|
| **Landing Page** | `github.com/oddsifylabs/alexbet-landing` | Static Site | Documentation + marketing |
| **Bot** | `github.com/oddsifylabs/alexbet-signal-pro` | Node.js Worker | Telegram bot (scanning, signals, CLV) |

---

## 1. Landing Page Deployment

### Step 1: Create New Railway Project
1. Go to https://railway.app
2. Click **"New Project"**
3. Select **"Deploy from GitHub repo"**
4. Choose: `oddsifylabs/alexbet-landing`
5. Name it: `AlexBET Landing`

### Step 2: Verify Build Configuration
The repo already includes `railway.json` with correct settings:
```json
{
  "build": { "builder": "STATIC" },
  "deploy": {
    "startCommand": "npx serve .",
    "staticDirectory": ".",
    "healthcheckPath": "/"
  }
}
```

### Step 3: Deploy
1. Click **"Deploy"**
2. Wait for build to complete (~2-3 minutes)
3. Copy the generated URL (e.g., `alexbet-landing-production.up.railway.app`)

### Step 4: Verify
- [ ] Open the URL in browser
- [ ] Confirm landing page loads with dark theme
- [ ] Click "Open Bot on Telegram" → opens @AlexBetSignalPro
- [ ] Click "Read the Guide" → opens HOWTO.md

### Step 5: (Optional) Custom Domain
If using custom domain:
1. Go to **Settings** → **Domains**
2. Add your domain (e.g., `alexbet.oddsifylabs.com`)
3. Update DNS records as instructed

---

## 2. Bot Deployment

### Step 1: Open Existing Railway Project
1. Go to your existing bot project on Railway
2. OR create new project from `oddsifylabs/alexbet-signal-pro`

### Step 2: Configure Environment Variables
Go to **Variables** tab and add:

| Variable | Value | Required |
|----------|-------|----------|
| `ODDS_API_KEY` | Your The-Odds-API key | ✅ YES |
| `TELEGRAM_BOT_TOKEN` | From @BotFather | ✅ YES |
| `SUPABASE_URL` | Your Supabase project URL | Optional |
| `SUPABASE_KEY` | Your Supabase API key | Optional |
| `WHOP_API_KEY` | Whop payment integration | Optional |

**⚠️ CRITICAL:** Bot will crash-loop without `ODDS_API_KEY` and `TELEGRAM_BOT_TOKEN`.

### Step 3: Verify Deployment Settings
- **Builder:** Nixpacks (auto-detected for Node.js)
- **Start Command:** `npm start` (from Procfile)
- **Node Version:** 20.x (from package.json)

### Step 4: Deploy
1. Click **"Deploy"** (or auto-deploys on push to main)
2. Watch logs for startup messages
3. Look for: `✅ Bot online: @AlexBetSignalPro`

### Step 5: Test Bot Commands
Open @AlexBetSignalPro on Telegram and test:
- [ ] `/scan` — Returns quality-graded signals (or "no signals" if market efficient)
- [ ] `/scanby` — Sport-specific scanning
- [ ] `/performance` — ROI dashboard
- [ ] `/clv` — Your CLV stats
- [ ] `/guide` — Should link to landing page (update after Step 6)

### Step 6: Update /guide Link
Once landing page is live, update the bot:

```bash
cd ~/alexbet-signal-pro
# Edit src/handlers/guide.js
# Change URL to new landing page
git commit -m "Update /guide to point to landing page"
git push origin main
```

Railway will auto-deploy on push.

---

## 3. Post-Deployment Verification

### Landing Page
- [ ] URL loads without errors
- [ ] All sections render (features, tiers, commands, FAQ)
- [ ] "Open Bot" button works
- [ ] "Read the Guide" link opens HOWTO.md
- [ ] Mobile responsive (test on phone)
- [ ] Footer links work (Website, Community)

### Bot
- [ ] Bot responds to `/start`
- [ ] `/scan` returns signals or appropriate "no signals" message
- [ ] Auto-settlement cron running (check logs every 30 min)
- [ ] A+ alerts cron running (check logs every 5 min)
- [ ] No crash loops in Railway logs
- [ ] No `ODDS_API_KEY not set` errors

### Integration
- [ ] `/guide` in bot → opens landing page
- [ ] Landing page "Open Bot" → opens Telegram
- [ ] Landing page "Read the Guide" → opens HOWTO.md

---

## 4. Troubleshooting

### Bot Crash Loop
**Symptom:** Logs show `❌ CRITICAL: ODDS_API_KEY not set in .env`

**Fix:**
1. Go to Railway project → Variables tab
2. Add `ODDS_API_KEY` with your API key
3. Add `TELEGRAM_BOT_TOKEN` with bot token
4. Restart deployment (Redeploy button)

### Landing Page 404
**Symptom:** URL shows 404 or blank page

**Fix:**
1. Check Railway build logs for errors
2. Verify `railway.json` has `"builder": "STATIC"`
3. Confirm `index.html` exists in repo root
4. Try manual redeploy

### Bot Commands Not Responding
**Symptom:** Bot online but commands timeout

**Fix:**
1. Check Railway logs for errors
2. Verify `TELEGRAM_BOT_TOKEN` is correct
3. Check rate limits (free tier: limited requests/min)
4. Restart bot deployment

### HOWTO.md Not Loading
**Symptom:** "Read the Guide" link 404s

**Fix:**
1. Confirm HOWTO.md exists in repo root
2. Railway static builder should serve .md files
3. If not, convert to HTML or use GitHub raw URL

---

## 5. URLs to Track

| Resource | URL | Status |
|----------|-----|--------|
| Landing Page | `https://[REPLACE].up.railway.app` | ⏳ Pending |
| Bot Repo | `https://github.com/oddsifylabs/alexbet-signal-pro` | ✅ Ready |
| Landing Repo | `https://github.com/oddsifylabs/alexbet-landing` | ✅ Ready |
| Bot on Telegram | `https://t.me/AlexBetSignalPro` | ✅ Live |

---

## 6. Next Steps After Deployment

1. **Update Memory:** Save landing page URL to Hermes memory
2. **Update Bot:** Change `/guide` handler to point to landing page
3. **Test Flow:** Bot → Landing Page → HOWTO.md → Bot
4. **Monitor:** Watch Railway logs for first 24 hours
5. **Announce:** Post landing page URL to Telegram channel

---

**Last Updated:** May 9, 2026  
**Bot Version:** 3.0.0  
**Landing Version:** 1.0.0
