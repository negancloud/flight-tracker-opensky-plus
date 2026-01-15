# Flight Tracker (OpenSky) — Polished “Plus” build

This version includes a more polished UI and the feature ideas you asked for:
- Dark mode + mobile bottom-sheet layout
- Aircraft “semi by size” scaling (heuristics + speed/altitude)
- Smooth movement (interpolated animation between 10s polls)
- Stale fade (aircraft fade as updates get old)
- Watchlist (saved to localStorage)
- Alerts (in-app toasts) for:
  - Aircraft disappears (watched / overhead candidates)
  - Route change / deviation (big heading change)
- “What’s overhead” mode using phone location (closest aircraft list)
- Lightweight traffic heat overlay (grid-based)
- Quick stats (count / airborne / ground / highest / fastest)
- Basic PWA hooks (manifest + simple service worker + install button)

## Requirements
- Node.js 18+

## Run locally
```bash
cd flight-tracker-opensky-plus
npm install
npm --prefix server install
npm --prefix web install
npm run dev
```
Web: http://localhost:5173

## Notes
- This is still ADS‑B derived (OpenSky). Some aircraft will disappear due to coverage gaps; the app treats that as a *feature* via alerts/fade.
- Alerts are “in-app” (toast notifications). Browser push notifications can be added later once you deploy over HTTPS.
