# VEGA Terminal — Claude Code Rules

## Project Overview
VEGA Terminal is a **single-file SPA** (`index.html`) — an investment intelligence dashboard.
No build tools. No framework. No backend. Everything ships in one HTML file.

| | |
|---|---|
| **Primary file** | `index.html` (all HTML + CSS + JS inline) |
| **Dev server** | `node serve.mjs` → http://localhost:3000 |
| **Data source** | TradingView Widgets (CDN embeds) |
| **Live prices** | Optional via Finnhub API key (see `VEGA_CONFIG` in index.html) |
| **State** | `localStorage` for watchlist (`vega_wl`) |

## Always Do First
- **Invoke the `frontend-design` skill** before writing any frontend code, every session, no exceptions.

## Architecture Rules
- All code lives in `index.html` — never split into separate files unless explicitly asked
- Brand color `#c9780c` (amber) is the only primary accent — never substitute with blue/indigo
- CSS variables live in `:root` — always use them, never hardcode hex values elsewhere
- TradingView embed widgets are the only external data source for market data
- Prices in the New Ideas tab are **illustrative** unless a `finnhubKey` is set in `VEGA_CONFIG`

## Local Server
- **Always serve on localhost** — never screenshot a `file:///` URL
- Start: `node serve.mjs` (serves project root at http://localhost:3000)
- Do not start a second instance if already running

## Screenshot Workflow
Personal screenshot tool paths live in `CLAUDE.local.md` (gitignored — not committed).
Create `CLAUDE.local.md` on your machine with your Puppeteer path.

Standard command: `node screenshot.mjs http://localhost:3000`
Screenshots save to `./temporary screenshots/screenshot-N.png` (auto-incremented, never overwritten).

After screenshotting, read the PNG with the Read tool and compare against reference:
- Check: spacing/padding, font sizes, colors (exact hex), alignment, border-radius, shadows
- Do at least **2 comparison rounds** — stop only when no visible differences remain or user confirms

## Design System

| Token | Variable | Value |
|---|---|---|
| Primary accent | `--amber` | `#c9780c` |
| Background | `--cream` | `#fafaf8` |
| Surface | `--white` | `#ffffff` |
| Ink | `--ink` | `#1c1917` |
| Muted | `--muted` | `#a8a29e` |
| Green | `--green` | `#15803d` |
| Red | `--red` | `#b91c1c` |
| Heading font | | Syne (700 / 800) |
| Data font | | JetBrains Mono |
| Body font | | DM Sans |

## Anti-Generic Guardrails
- Never use default Tailwind palette (indigo-500, blue-600, etc.)
- Never use flat `shadow-md` — use layered, color-tinted shadows with low opacity
- Never use the same font for headings and body
- Never use `transition-all` — animate only `transform` and `opacity`
- Every clickable element needs hover, focus-visible, and active states

## Hard Rules
- Single `index.html` — all styles inline
- No comments unless the WHY is non-obvious
- Do not add features beyond what is explicitly asked
- Never present hardcoded prices as "real-time" without a live API key configured
