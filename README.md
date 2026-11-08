# Meter Running

Live earnings meter: stopwatch with laps and per-lap hourly rates, gross USD ticking up in real time,
CAD at the daily mid-market rate, and net-to-bank after PayPal fees and conversion spread.

Installable web app (PWA). No build step, no dependencies.

## Hosting (free, 5 minutes)

1. Create a new public GitHub repository and upload these files (`index.html`, `manifest.webmanifest`, `sw.js`, `icon-192.png`, `icon-512.png`).
2. Repository **Settings → Pages → Source: Deploy from a branch**, branch `main`, folder `/ (root)`. Save.
3. Your app is at `https://<you>.github.io/<repo>/` within a minute or two.

Any static host over HTTPS works the same (Netlify, Cloudflare Pages).

## Installing as an app

- **Chromebook / desktop Chrome**: open the URL, click the install icon at the right of the address bar (or menu → *Install Meter Running*).
- **Android Chrome**: menu → *Add to Home screen* → *Install*.
- **iPhone Safari**: Share → *Add to Home Screen*.

## Exchange rate

Rates come from api.frankfurter.dev (European Central Bank reference rates), with open.er-api.com as a fallback.
Neither needs an API key. Both publish about once a day; the app re-checks hourly while open and when it comes
back online. Untick *Update automatically* in Settings to enter your own rate.

PayPal does not convert at the mid-market rate. Set the *conversion spread* to the gap between the mid-market
rate and what your transfers actually get.

## Data

Session, laps and settings are stored in the browser (localStorage) on each device; they do not sync between devices.
