# VEGA Terminal — AI Investment Intelligence Dashboard

A sleek, terminal-style investment dashboard that helps you allocate capital intelligently across top stocks using AI-curated strategies, confidence scoring, and projected returns.

> Built as a single `index.html` — no backend, no build step, runs instantly in any browser.

---

## Features

### Investment Calculator
- Input any amount (default $1,000) and see it allocated across top stock picks
- **4 investment strategies** tailored to different risk profiles:
  - **Conservative** — Dividend aristocrats & blue chips (8–12% projected)
  - **Balanced** — Growth + income blend (14–20% projected)
  - **Growth** — High-conviction tech plays (25–45% projected)
  - **Aggressive** — Maximum upside, elevated risk (40–80% projected)

### Stock Intelligence Cards
Each recommendation includes:
- Ticker, company name, and sector
- Dollar allocation based on your investment amount
- **Confidence score** with animated color-coded bar (green → yellow → red)
- **Investment thesis** — concise reasoning for the pick
- 12-month projected return and outcome value

### Portfolio Summary Panel
- Live donut chart showing allocation breakdown
- Projected portfolio value range
- Expected gain range
- Average confidence score
- Visual risk-level meter (Low → Very High)

### Live Market Data
- **Ticker tape** — real-time prices for indices, crypto, forex, and major stocks
- **Global Markets panel** — TradingView market overview (Indices, Futures, Crypto, Forex)
- **Stock Screener** — filterable by market (US/Crypto/Forex/Futures) and screen (Volume/Gainers/Losers)
- **Watchlist** — add/remove symbols, persisted in localStorage

---

## Getting Started

### Option 1 — Open directly
Just open `index.html` in any modern browser. No installation needed.

### Option 2 — Local server (recommended)
```bash
node serve.mjs
```
Then visit `http://localhost:3000`

> Requires Node.js 18+

---

## Tech Stack

| Layer | Details |
|---|---|
| Frontend | Vanilla HTML + CSS + JavaScript |
| Fonts | Syne (headings) · JetBrains Mono (data) · DM Sans (body) |
| Market Data | TradingView Widgets (ticker tape, market overview, screener) |
| State | localStorage (watchlist persistence) |
| Server | Node.js built-in `http` module (`serve.mjs`) |

Zero dependencies. Zero frameworks. Zero build tools.

---

## Strategy Details

### Conservative
> Allocation: MSFT 25% · AAPL 20% · JNJ 20% · PG 20% · KO 15%

Low volatility, dividend-focused holdings with decades of stability. Ideal for capital preservation with modest growth.

### Balanced
> Allocation: NVDA 25% · MSFT 20% · AMZN 20% · JPM 20% · META 15%

Equal blend of AI-era growth leaders and established income generators. Best risk-adjusted return profile.

### Growth
> Allocation: NVDA 30% · META 25% · AMZN 20% · GOOGL 15% · TSLA 10%

High-conviction technology and innovation plays. Concentrated in companies with structural AI tailwinds.

### Aggressive
> Allocation: NVDA 25% · PLTR 20% · ARM 20% · TSLA 20% · SMCI 15%

Maximum upside potential with elevated volatility. For conviction investors with a 12+ month time horizon.

---

## Confidence Score Methodology

| Score | Color | Interpretation |
|---|---|---|
| 90–100% | Green | Very high conviction — strong fundamentals + technical setup |
| 80–89% | Yellow | High conviction — solid thesis with minor uncertainties |
| 70–79% | Orange | Moderate conviction — upside present, execution risk exists |
| Below 70% | Red | Speculative — asymmetric upside but meaningful downside risk |

---

## Design

Terminal-inspired dark UI with amber accent palette:

- **Background:** `#07080a` deep black with scanlines + film grain overlay
- **Accent:** `#f5a623` amber/orange
- **Typography:** Syne for display, JetBrains Mono for data, DM Sans for prose
- **Animations:** CSS keyframe card reveal, confidence bar fill, SVG donut chart

---

## Disclaimer

This dashboard is for **educational and informational purposes only**. The stock picks, confidence scores, and projected returns shown are illustrative and do not constitute financial advice. Always conduct your own research before making investment decisions.

---

## License

MIT — free to use, modify, and distribute.

---

*Built with Claude Code*
