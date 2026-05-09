# 🚀 Deploy Instructions for AlexBET Landing Page

## Repository Created ✅

Files ready in: `~/alexbet-landing/`

## Manual Push to GitHub

Since the repo already exists on your account, follow these steps:

### Option 1: Push from Your Local Machine

```bash
# Clone the existing repo
git clone https://github.com/oddsifylabs/alexbet-signal-pro.git
cd alexbet-signal-pro

# Copy landing page files from this machine
# (Download from ~/alexbet-landing/ or I can send you a zip)

# Add and commit
git add .
git commit -m "Add landing page and how-to guide"
git push origin main
```

### Option 2: GitHub Web Upload

1. Go to: **https://github.com/oddsifylabs/alexbet-signal-pro**
2. Click **"Add file"** → **"Upload files"**
3. Upload these 6 files:
   - `index.html` (landing page)
   - `README.md` (documentation)
   - `HOWTO.md` (how-to guide)
   - `package.json` (Railway deps)
   - `railway.json` (Railway config)
   - `.gitignore`
4. Commit changes

### Option 3: Use GitHub CLI (if installed)

```bash
cd ~/alexbet-landing
gh repo sync oddsifylabs/alexbet-signal-pro
git push origin main
```

---

## Deploy to Railway

Once files are on GitHub:

### Step 1: Create Railway Project

1. Go to: **https://railway.app**
2. Click **"New Project"**
3. Select **"Deploy from GitHub repo"**
4. Choose: **`oddsifylabs/alexbet-signal-pro`**

### Step 2: Configure Deployment

Railway will auto-detect the `railway.json` config. Verify:

- **Build:** Static builder
- **Start Command:** `npx serve .`
- **Root Directory:** `./`

### Step 3: Deploy

Click **"Deploy"** — Railway will build and host your landing page.

### Step 4: Get Your URL

After deployment (~2 minutes), you'll get:
- **Production URL:** `https://alexbet-signal-pro-production.up.railway.app`
- **Custom Domain:** (optional) Connect `www.oddsifylabs.com`

---

## Update Bot to Use New Landing Page

Once deployed, update the bot's `/guide` command:

### File to Edit
`~/alexbet-signal-pro/src/handlers/guide.js` (or wherever `/guide` is defined)

### Change From:
```javascript
bot.sendMessage(chatId, '📘 How-To Guide: https://github.com/oddsifylabs/alexbet-signal-pro/blob/main/HOWTO.md');
```

### Change To:
```javascript
bot.sendMessage(chatId, '📘 How-To Guide: https://alexbet-signal-pro-production.up.railway.app/#faq\n\n📖 Full Documentation: https://alexbet-signal-pro-production.up.railway.app');
```

---

## Files Summary

| File | Purpose | Size |
|------|---------|------|
| `index.html` | Landing page (dark theme, responsive) | 27 KB |
| `README.md` | GitHub repo documentation | 9.5 KB |
| `HOWTO.md` | Complete how-to guide | 12 KB |
| `package.json` | Railway deployment deps | 237 B |
| `railway.json` | Railway config | 313 B |
| `.gitignore` | Git ignore rules | 159 B |

---

## Landing Page Features

✅ **Responsive Design** — Works on mobile, tablet, desktop  
✅ **Dark Theme** — Matches Telegram bot aesthetic  
✅ **Hero Section** — CTA buttons to launch bot  
✅ **Stats Bar** — 40+ sports, 11 books, 3 markets, 4% EV  
✅ **Features Grid** — 9 elite features with icons  
✅ **Tier Cards** — A+/A/B comparison with specs  
✅ **Commands Section** — All bot commands organized  
✅ **FAQ Section** — 7 common questions answered  
✅ **Footer** — Links, disclaimer, copyright  

---

## Next Steps

1. ✅ Push files to GitHub (use one of the methods above)
2. ✅ Deploy to Railway (connect GitHub repo)
3. ✅ Get Railway production URL
4. ✅ Update bot's `/guide` command with new URL
5. ✅ Test landing page loads correctly
6. ✅ (Optional) Connect custom domain `www.oddsifylabs.com`

---

**Questions?** Reply in Telegram or email support@oddsifylabs.com
