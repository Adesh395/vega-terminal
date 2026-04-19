# VEGA Terminal — Investment Intelligence Dashboard

A terminal-style investment dashboard with live TradingView charts, US market movers, AI-curated stock ideas, and top analyst picks. Built as a **single `index.html`** — no build step, no dependencies, runs in any browser.

---

## Quick Start

```bash
# Clone the repo
git clone https://github.com/YOUR_USERNAME/vega-terminal.git
cd vega-terminal

# Start the dev server (requires Node.js 18+)
node serve.mjs
```

Open **http://localhost:3000** in Chrome.

> **No Node.js?** Just open `index.html` directly in your browser. All features work — the server is optional and only needed for screenshot tooling.

---

## Features

### Dashboard
- **Live Candlestick Chart** — TradingView Advanced Chart (all timeframes: 1m → 1W)
- **Watchlist** — add/remove symbols, persisted across sessions via localStorage
- **Top Movers** — US market gainers, losers, and volume leaders (TradingView Hotlists widget)

### New Ideas
- Enter any investment amount and choose a **risk profile** (Conservative → Aggressive)
- Choose a **technical strategy** (Elliott Wave, RSI Divergence, MACD, Bollinger Bands, Golden Cross)
- Get AI-curated stock picks with:
  - Current price · Target price · Upside %
  - Individual stock risk level (LOW / MEDIUM / HIGH / VERY HIGH)
  - Confidence score with animated bar
  - Investment thesis
  - 12-month projection
- **Portfolio Breakdown** sidebar: donut chart, projected value range, risk meter

### Top Traders
- Curated profiles of top TradingView analysts
- Their specialties, follower counts, accuracy rates
- Current conviction picks (Bullish / Bearish / Watching)
- Published investment thesis

---

## Live Price Configuration (Optional)

By default, stock prices in **New Ideas** are research-based estimates labeled `EST.`

To enable **live prices** (labeled `LIVE`):

1. Get a **free** API key at [finnhub.io/register](https://finnhub.io/register) — no credit card required
2. Open `index.html`, find the `VEGA_CONFIG` block near the top of the `<script>` section:

```js
const VEGA_CONFIG = {
  finnhubKey: '', // ← paste your key here
};
```

3. Save. Reload. Prices update automatically when you open New Ideas.

> Free Finnhub tier: 60 calls/minute. Covers all stocks in all 4 strategies.

---

## Project Structure

```
vega-terminal/
├── index.html              ← Entire app (HTML + CSS + JS, single file)
├── serve.mjs               ← Dev server (Node.js built-in http module)
├── CLAUDE.md               ← Claude Code project rules (committed)
├── CLAUDE.local.md         ← Personal overrides — Puppeteer paths, API keys (gitignored)
├── README.md
├── .gitignore
└── .claude/
    ├── settings.json       ← Project-level Claude Code permissions (committed)
    ├── settings.local.json ← Personal permissions overrides (gitignored)
    └── commands/
        ├── screenshot.md   ← /project:screenshot — take + analyze a screenshot
        ├── serve.md        ← /project:serve — start dev server
        └── deploy.md       ← /project:deploy — push to GitHub Pages
```

---

## Tech Stack

| Layer | Details |
|---|---|
| Frontend | Vanilla HTML · CSS · JavaScript (no framework) |
| Fonts | Syne · JetBrains Mono · DM Sans (Google Fonts CDN) |
| Market Data | TradingView Widgets (ticker tape, advanced chart, hotlists) |
| Live Prices | Finnhub API (optional, free tier) |
| State | `localStorage` for watchlist persistence |
| Server | Node.js `http` module (`serve.mjs`) |

**Zero npm dependencies. Zero build tools. Zero config.**

---

## Deploying to GitHub Pages

1. Push to GitHub
2. Go to **Settings → Pages → Source** → set to `main` branch, root (`/`)
3. Save — your site is live at `https://YOUR_USERNAME.github.io/REPO_NAME/`

Or use the Claude Code command: `/project:deploy`

---

## Claude Code Setup (for contributors)

This project is configured for [Claude Code](https://claude.ai/code):

- `CLAUDE.md` — project rules loaded every session
- `.claude/commands/` — custom slash commands (`/project:screenshot`, `/project:serve`, `/project:deploy`)
- `.claude/settings.json` — project-level tool permissions

**Personal setup:** Create `CLAUDE.local.md` in the project root (gitignored) with your local Puppeteer path and optional Finnhub key. See `CLAUDE.local.md` in this repo for the template format.

---

## New Ideas — Strategy Details

### Conservative · 8–12% projected
> MSFT 25% · AAPL 20% · JNJ 20% · PG 20% · KO 15%

Dividend aristocrats and blue chips with decades of proven stability. For capital preservation with modest growth.

### Balanced · 14–20% projected
> NVDA 25% · MSFT 20% · AMZN 20% · JPM 20% · META 15%

AI-era growth leaders blended with established income generators. Best risk-adjusted return profile.

### Growth · 25–45% projected
> NVDA 30% · META 25% · AMZN 20% · GOOGL 15% · TSLA 10%

High-conviction technology and innovation plays with structural AI tailwinds.

### Aggressive · 40–80% projected
> NVDA 25% · PLTR 20% · ARM 20% · TSLA 20% · SMCI 15%

Maximum upside with elevated volatility. For conviction investors with 12+ month horizon.

---

## Confidence Score Guide

| Score | Color | Meaning |
|---|---|---|
| 90–100% | Green | Very high conviction — strong fundamentals + technical setup |
| 80–89% | Amber | High conviction — solid thesis, minor uncertainties |
| 70–79% | Orange | Moderate conviction — upside present, execution risk exists |
| < 70% | Red | Speculative — asymmetric upside but meaningful downside risk |

---

## Disclaimer

**For educational and informational purposes only.** Stock picks, confidence scores, and projected returns are illustrative and do not constitute financial advice. Always conduct your own research before making investment decisions.

---

## License

MIT — free to use, modify, and distribute.

---

*Built with [Claude Code](https://claude.ai/code)*
