# Baby Tracker

A minimal, mobile-first Progressive Web App for tracking newborn feeds and temperatures. Built as a single HTML file — no build step, no dependencies, no server required.

## Features

- **Feed tracker** — log left or right breast with one tap; shows last feed with relative time and today's count
- **Temperature tracker** — log readings with color-coded status (normal / slightly elevated / fever ≥ 38°C)
- **History** — chronological log grouped by day, filterable by type, with per-entry delete
- **Offline** — fully self-contained, works without internet after first load
- **Persistent** — all data stored in LocalStorage, survives browser restarts
- **Installable** — add to home screen on both iOS and Android for a native app feel

## Files

```
Baby App/
├── index.html     # Complete app (HTML + CSS + JS)
├── sw.js          # Service worker (offline caching)
└── manifest.json  # PWA manifest (icons, display mode)
```

## Deployment

Drop all three files into the same folder on any static host:

- [GitHub Pages](https://pages.github.com)
- [Netlify](https://netlify.com) — drag & drop the folder
- [Vercel](https://vercel.com)

The app must be served over **HTTPS** for the service worker and install prompt to work (localhost works too).

## Installing on your phone

**iOS (Safari)**
1. Open the URL in Safari
2. Tap the Share button → **Add to Home Screen**
3. Tap **Add**

**Android (Chrome)**
1. Open the URL in Chrome
2. Tap the menu (⋮) → **Add to Home Screen** or wait for the install banner

## Temperature thresholds

| Range | Status |
|---|---|
| 36.5 – 37.5 °C | Normal |
| 37.5 – 38.0 °C | Slightly elevated |
| ≥ 38.0 °C | Fever — contact your doctor |

## Local development

No build step needed. Serve locally with any static server, for example:

```bash
npx serve .
# or
python3 -m http.server 8080
```

Then open `http://localhost:8080` in your browser.
