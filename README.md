# SFTi · Market Lens

> **AI-powered trading screenshot analyzer with real-time market session tracking.**  
> A single-file, zero-install progressive web app built for traders who need fast, dense delta analysis from their charts.

---

## Overview

SFTi Market Lens is a client-side web application (`index.html`) that lets you drop trading screenshots onto a canvas, then fire them through the Anthropic Claude API to get a concise, data-dense analysis — price levels, % changes, session transitions, momentum patterns, and full delta reports across multiple screenshots.

Everything runs in the browser. No backend. No data leaves your device except for the API call to `api.anthropic.com`.

---

## Features

| Feature | Detail |
|---|---|
| **Live Market Bar** | Floating header shows current ET + CST time and color-coded session label — Overnight, Pre-Market, Market Open, After Hours |
| **Session Timeline** | Visual progress bar segmented by trading session (4:00 AM → 9:30 AM → 4:00 PM → 8:00 PM ET), with a live cursor |
| **Draggable Image Cards** | Upload one or many screenshots; each spawns as a draggable, resizable card on the canvas |
| **Pinch-to-Resize** | Two-finger pinch gesture resizes cards on touch devices |
| **OPFS Persistence** | Screenshots are written to the browser's Origin Private File System, keyed by date, so they survive refreshes |
| **Claude AI Analysis** | Single screenshot → full data extraction. Multiple screenshots → delta report with ▲/▼ moves, session transitions, added/removed tickers |
| **Session-stored API Key** | Your `sk-ant-` key lives only in `sessionStorage` — cleared when the tab closes, never persisted to disk or sent anywhere except Anthropic |
| **Long-press to Re-key** | Hold the eye bubble for 700 ms to re-enter your API key without reloading |
| **Toast Notifications** | Lightweight in-app toasts confirm uploads, key saves, and errors |
| **PWA-ready** | `apple-mobile-web-app-capable` meta tags for full-screen iOS home-screen install |

---

## Tech Stack

- **Vanilla HTML / CSS / JavaScript** — zero dependencies, zero build step
- **Anthropic Messages API** (`claude-3-5-sonnet` / vision) — multi-image base64 payloads
- **Origin Private File System (OPFS)** — browser-native file storage
- **Google Fonts** — Orbitron (headers) + JetBrains Mono (body)
- **CSS custom properties + `backdrop-filter`** — liquid-glass UI with iridescent bubble controls

---

## Getting Started

### Run locally

```bash
# Any static file server works — no build required
npx serve .
# or
python3 -m http.server 8080
```

Then open `http://localhost:8080` in your browser.

### Deploy

Drop `index.html` on any static host (GitHub Pages, Netlify, Vercel, Cloudflare Pages). No server-side code needed.

---

## Usage

1. **Open the app** — the market bar auto-detects the current session.
2. **Add screenshots** — tap the photo bubble (bottom-left) and select one or more trading chart images.
3. **Enter your Anthropic API key** — paste your `sk-ant-...` key when prompted. Get one at [console.anthropic.com](https://console.anthropic.com) → API Keys.
4. **Analyze** — tap the eye bubble (bottom-center). Results slide up in the analysis panel.
5. **Long-press the eye bubble** to update your API key at any time.

---

## Market Sessions (ET)

| Session | Window |
|---|---|
| Overnight | 8:00 PM → 4:00 AM |
| Pre-Market | 4:00 AM → 9:30 AM |
| Market Open | 9:30 AM → 4:00 PM |
| After Hours | 4:00 PM → 8:00 PM |

---

## Privacy

- Your API key is stored in `sessionStorage` only — it is cleared when the browser tab is closed.
- Screenshot data is never sent anywhere except the Anthropic API for analysis.
- No analytics, no telemetry, no external requests beyond Google Fonts and `api.anthropic.com`.

---

## Support

If this tool saves you time, consider supporting development:

[![GitHub Sponsors](https://img.shields.io/badge/Sponsor-GitHub-ea4aaa?logo=github)](https://github.com/sponsors/statikfintechllc)
[![Patreon](https://img.shields.io/badge/Patreon-StatikFinTech-f96854?logo=patreon)](https://patreon.com/StatikFinTech_LLC)
[![Ko-fi](https://img.shields.io/badge/Ko--fi-Buy%20a%20Coffee-ff5e5b?logo=ko-fi)](https://ko-fi.com/statikfintech_llc)
[![PayPal](https://img.shields.io/badge/PayPal-statikmoney8-003087?logo=paypal)](https://paypal.me/statikmoney8)
[![Cash App](https://img.shields.io/badge/Cash%20App-%24statikmoney8-00d54b?logo=cashapp)](https://cash.app/$statikmoney8)

---

## License

© StatikFinTech LLC. All rights reserved.