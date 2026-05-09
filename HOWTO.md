# 📘 AlexBET Signal Pro — How-To Guide

**Version 3.0 | Updated: May 2026**

---

## Table of Contents

1. [Getting Started](#getting-started)
2. [Running Your First Scan](#running-your-first-scan)
3. [Understanding Signal Cards](#understanding-signal-cards)
4. [Filtering Signals](#filtering-signals)
5. [Book Preferences](#book-preferences)
6. [Push Notifications](#push-notifications)
7. [Performance Tracking](#performance-tracking)
8. [CLV & Leaderboards](#clv--leaderboards)
9. [Exporting Data](#exporting-data)
10. [Subscription Tiers](#subscription-tiers)
11. [Troubleshooting](#troubleshooting)
12. [Best Practices](#best-practices)

---

## Getting Started

### Step 1: Open the Bot

1. Click: [**t.me/AlexBetSignalPro**](https://t.me/AlexBetSignalPro)
2. Tap **"START"** or send `/start`
3. You'll see your account info and subscription tier

### Step 2: Understand Your Tier

Free tier users see:
- 3 scans per day
- Moneyline markets only

Paid tiers unlock:
- More scans per day
- Spread and Total markets
- A+ push notifications

### Step 3: Set Your Bankroll (Optional)

The bot defaults to $100 bankroll for staking recommendations. To update:
- Contact support via `/support`
- Or set via web dashboard (coming soon)

---

## Running Your First Scan

### Basic Scan

Send: `/scan`

You'll receive:
1. **Summary card** — Total signals, tier breakdown, top signal
2. **Individual signal cards** — Each bet with full metrics
3. **Filter keyboard** — Buttons to refine results

### Sport-Specific Scan

Send: `/scanby NBA`

Supported sports:
- `NBA`, `NFL`, `MLB`, `NHL`
- `EPL`, `UCL`, `MLS`, `Bundesliga`, `La Liga`, `Serie A`
- `NCAAF`, `NCAAB`, `College Baseball`
- `ATP`, `WTA`, `MMA`, `Boxing`
- And 30+ more!

### When No Signals Appear

If you see:
> ⏳ No signals meeting quality standards right now...

This means:
- Markets are efficient (no +EV opportunities)
- The bot is working correctly (not forcing bad bets)
- Try again in a few hours

**This is a feature, not a bug.** Quality over quantity.

---

## Understanding Signal Cards

### A+ Elite Signal Example

```
🟢🟢🟢 🏆 A+ ELITE SIGNAL 🟢🟢🟢
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

#1 — NBA 🏀
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

🎯 SIGNAL
Lakers +6.5 @ *+110*
Line Movement: 📈 +2.3%
Market: Spread | Type: Away Team

📊 GAME INFO
Boston Celtics vs Los Angeles Lakers
📅 2026-05-09 at 8:00 PM ET (3h)

💰 VALUE METRICS
Edge: *+9.2%* | EV: *+8.7%*
Fair Prob: *52.3%*
Books Compared: *7*

📍 WHERE TO BET
Best Book: *DraftKings*

💵 STAKING RECOMMENDATIONS
Kelly (5% cap): *$5.00*
Conservative 2%: *$2.00*
Conservative 1.5%: *$1.50*
Conservative 1%: *$1.00*

📈 QUALITY SCORE: 9.2/10
🟩🟩🟩🟩🟩🟩🟩🟩🟩⬜

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

### Key Metrics Explained

| Metric | What It Means |
|--------|---------------|
| **Edge** | Difference between your odds and fair odds |
| **EV** | Expected Value — long-term profit % per bet |
| **Fair Prob** | True win probability after removing vig |
| **Books Compared** | How many sportsbooks were scanned |
| **Kelly** | Optimal stake based on edge (capped at 5%) |
| **Quality Score** | Composite of EV, books, time to game (1-10) |
| **Line Movement** | How odds changed since first scanned |

### Quality Tiers

| Tier | Badge | Min EV | Min Books | Max Time |
|------|-------|--------|-----------|----------|
| **A+ Elite** | 🏆 | 8%+ | 5+ | <24h |
| **A High** | ⭐ | 6%+ | 4+ | <36h |
| **B Standard** | ✓ | 4%+ | 3+ | <48h |

---

## Filtering Signals

### Using Inline Keyboards

After a scan, you'll see filter buttons:

```
┌─────────────────────────────────────────┐
│ 🟢 A+ (2)  │  🔵 A (3)  │  🟡 B (5)    │  ← Tier
│ 🎯 ML  │  📊 Spread  │  📈 Total     │  ← Market
│ NBA  │  MLB  │  NHL  │  EPL          │  ← Sport
│      🔄 Re-scan      │  📤 Export     │  ← Actions
└─────────────────────────────────────────┘
```

**Tap any button** to filter instantly:
- `🟢 A+ (2)` — Show only A+ Elite signals
- `📊 Spread` — Show only spread bets
- `NBA` — Show only NBA signals
- `🔄 Re-scan` — Fresh scan of all sports
- `📤 Export` — Download current results

### Book Filtering

If you set preferred books (see below), signals not available at your books are automatically excluded.

---

## Book Preferences

### Why Set Books?

The bot scans 11 US sportsbooks, but you may only have accounts at a few. Set your books to see **only signals you can actually bet**.

### How to Set Books

1. Send: `/setbooks`
2. You'll see a list of available books
3. Reply with book names (comma-separated):

```
DraftKings, FanDuel, BetMGM
```

### Available Books

- DraftKings
- FanDuel
- BetMGM
- Fanatics
- BetRivers
- Caesars
- William Hill
- BetOnline.ag
- BetUS
- Bovada
- LowVig.ag

### Clear Book Filters

Send: `/clearbooks`

Now you'll see all signals, regardless of book availability.

---

## Push Notifications

### Enable A+ Alerts

Get instant notifications for elite signals:

1. Send: `/setalerts a+`
2. You'll receive: "✅ A+ alerts enabled"

### What You'll Get

When an A+ Elite signal is found (8%+ EV, 5+ books, <24h):

```
🔔 A+ ELITE ALERT

🏆 Lakers +6.5 @ +110 (NBA)
Edge: +9.2% | EV: +8.7%
Book: DraftKings
Game: 3h from now

Tap to scan: /scan
```

### Disable Alerts

Send: `/setalerts off`

---

## Performance Tracking

### View Your Dashboard

Send: `/performance`

You'll see:
- **Overall Record** — Wins, losses, pushes, win rate
- **CLV Stats** — Average CLV, hit rate, positive count
- **ROI by Tier** — How A+/A/B signals perform
- **ROI by Market** — ML vs. Spread vs. Total profitability
- **Top Books** — Which sportsbooks give you best CLV

### Example Dashboard

```
📊 PERFORMANCE DASHBOARD
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

OVERALL RECORD
23W - 18L - 4P (56.1% win rate)

CLV PERFORMANCE
Avg CLV: +2.8% 🟢 Excellent
Hit Rate: 68% (beating market close)
Positive: 31 | Negative: 14

ROI BY QUALITY TIER
🏆 A+ Elite: 8-3-1 (72.7%) | ROI: +18.4%
⭐ A High: 10-9-2 (52.6%) | ROI: +6.2%
✓ B Standard: 5-6-1 (45.5%) | ROI: -2.1%

ROI BY MARKET
🎯 ML: 12-8-2 (60.0%) | ROI: +9.3%
📊 Spread: 7-6-1 (53.8%) | ROI: +4.1%
📈 Total: 4-4-1 (50.0%) | ROI: +1.2%

TOP SPORTSBOOKS BY CLV
1. DraftKings: +3.4% CLV
2. FanDuel: +2.9% CLV
3. BetMGM: +2.1% CLV
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

### Interpretation

- **CLV ≥ 3%** 🟢 = Excellent (you're beating the market)
- **CLV ≥ 1%** 🟡 = Good (sharp betting)
- **CLV ≥ 0%** 🟠 = Neutral (breaking even vs. market)
- **CLV < 0%** 🔴 = Negative (need to improve timing)

---

## CLV & Leaderboards

### What is CLV?

**Closing Line Value (CLV)** measures whether you got better odds than the final market price.

**Example:**
- You bet Lakers +6.5 @ +110
- Closing line: Lakers +4.5 @ -110
- You beat the line by 2 points = **Positive CLV**

Consistently positive CLV = long-term profitability, even before results are in.

### View Your CLV

Send: `/clv`

You'll see:
- Average CLV %
- Hit rate (how often you beat the close)
- Positive vs. negative CLV count
- CLV trend over time

### Global Leaderboards

Send: `/leaderboard`

Shows top users by average CLV:

```
🏆 CLV LEADERBOARD (Last 100 Signals)
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

1. @SharpBettor: +4.2% CLV 🟢
2. @VegasBeater: +3.8% CLV 🟢
3. @You: +2.8% CLV 🟢 ← YOU
4. @EVChaser: +2.1% CLV 🟡
5. @LineWatcher: +1.9% CLV 🟡

...

Minimum 10 signals to qualify
```

### Requirements

- Minimum **10 signals** to appear on leaderboard
- Rankings use **100-signal rolling average**
- Updates after each signal settles

---

## Exporting Data

### Export Formats

Export your latest scan in 3 formats:

| Format | Use Case |
|--------|----------|
| **JSON** | Import to spreadsheets, databases, analysis tools |
| **CSV** | Excel, Google Sheets, data analysis |
| **TXT** | Plain text, easy sharing |

### How to Export

After a scan:
1. Tap `📤 Export` button on filter keyboard
2. Or send: `/export_json`, `/export_csv`, `/export_txt`
3. File downloads to your device

### Export Contents

Each export includes:
- Signal details (team, market, odds)
- EV, edge, fair probability
- Quality tier, quality score
- Sportsbook, books compared
- Game date/time, hours to game
- Kelly stake, conservative stakes

---

## Subscription Tiers

| Tier | Scans/Day | Markets | Price |
|------|-----------|---------|-------|
| **Free** | 3 | Moneyline only | $0 |
| **Monthly** | 10 | ML + Totals | $29/mo |
| **Monthly Plus** | 30 | ML + Spread + Totals | $49/mo |
| **Yearly** | 20 | ML + Spread + Totals | $299/yr |
| **Lifetime** | Unlimited | All markets | $999 one-time |

### Upgrade

Send: `/subscribe` for upgrade link.

### Check Your Tier

Send: `/start` to see your current subscription.

---

## Troubleshooting

### "No signals found"

**Cause:** Markets are efficient — no +EV opportunities exist.

**Solution:** 
- Wait a few hours
- Try `/scanby` for specific sports
- This is normal — quality over quantity

### "Rate limited"

**Cause:** Too many scans in short time.

**Solution:**
- Wait the displayed time (usually 30-60 seconds)
- Free tier: 3 scans/day max
- Paid tiers: higher limits

### "No signals at YOUR books"

**Cause:** You set book filters, but signals are at other books.

**Solution:**
- Use `/clearbooks` to see all signals
- Or `/setbooks` to add more books

### Bot not responding

**Cause:** Temporary API outage or Railway restart.

**Solution:**
- Wait 1-2 minutes
- Check `/status` command
- Bot auto-restarts on failures

### Wrong staking amounts

**Cause:** Bankroll not set or outdated.

**Solution:**
- Contact `/support` to update bankroll
- Default is $100 if not set

---

## Best Practices

### 1. Only Bet A+ and A Signals

B signals are playable but lower EV. Stick to A+ and A for best long-term results.

### 2. Use Book Filters

Set `/setbooks` to your actual books. No point seeing signals you can't bet.

### 3. Enable A+ Alerts

`/setalerts a+` ensures you never miss the rarest, highest-EV opportunities.

### 4. Track Your CLV

Check `/clv` weekly. Positive CLV = you're betting sharp. Negative CLV = adjust timing.

### 5. Export for Analysis

Use `/export_csv` to track results in Excel. Identify which tiers/markets/books work best for you.

### 6. Respect Bankroll Management

Use the conservative staking recommendations:
- 2% for standard plays
- 1.5% for moderate confidence
- 1% for uncertain spots

Never chase losses or bet more than you can afford to lose.

### 7. Understand Variance

Even +EV bets lose. A 60% win rate means 40% losses. Don't tilt — trust the math.

### 8. Compare Multiple Books

Having accounts at 5+ books maximizes your ability to shop for best odds.

### 9. Bet Early, Not Late

Signals <24h to game have less variance. Avoid last-minute bets unless EV is exceptional.

### 10. Review Performance Monthly

Use `/performance` to see:
- Which tiers hit best
- Which markets you excel at
- Which books give best CLV

Adjust your strategy based on data, not gut feelings.

---

## Additional Resources

- **The Turtle Doctrine** — Methodology textbook by Jesse J. Collins
- **Oddsify Labs Website** — [www.oddsifylabs.com](https://www.oddsifylabs.com)
- **Testudo Legio Community** — [t.me/testudolegio](https://t.me/testudolegio)
- **Support** — `/support` in bot or support@oddsifylabs.com

---

**Built with 🐢 by Oddsify Labs | Queen Creek, AZ**

© 2026 Collins & Technologies. All rights reserved.
