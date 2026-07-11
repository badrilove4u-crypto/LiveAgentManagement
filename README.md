# Support Operations Command Center

A single-file, no-build HTML dashboard mockup for a Support Ops NOC-style display.

## Files
- `index.html` — the full dashboard (HTML + CSS + JS in one file, uses Chart.js from a CDN)

## Running it
No build step needed. Just open `index.html` in a browser, or serve the folder with any static file server, e.g.:

```
npx serve .
```
or
```
python3 -m http.server 8000
```

## What's inside
- Live KPI strip (calls, chats, tickets, waiting, CSAT, SLA breaches, critical, avg response)
- Agent Availability — Kanban-style columns by status, sourced conceptually from Zoho People
- Queue Health gauge + live queue stats
- Zoho Cliq channel summary (pings received / open / closed) for 5 named channels
- Live Alerts feed
- Trend charts (tickets/hr, chats & calls/hr, CSAT vs DSAT, occupancy)

All data is currently mocked/randomly generated client-side and refreshes every 60 seconds to simulate a live feed.
To go live, replace the `gen*()` functions in the `<script>` block with real fetch calls to your backend
(Zoho Desk / CRM / SalesIQ / Voice / Cliq / People APIs).

## Notes
- Dark theme, colorful accent system, designed to fit one screen without page scrolling on a monitor/TV.
- Falls back to a scrollable stacked layout on small/narrow windows (phones, split screens).

## Deploying to GitHub Pages
This repo includes `.github/workflows/pages.yml`, which publishes the site automatically on every push to `main`.

One-time setup after pushing to GitHub:
1. Go to the repo's **Settings → Pages**.
2. Under **Build and deployment → Source**, select **GitHub Actions**.
3. Push to `main` (or re-run the workflow from the **Actions** tab) — the site will be live at `https://<your-username>.github.io/<repo-name>/`.
