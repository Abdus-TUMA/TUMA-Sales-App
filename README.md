# TUMA Lead Dashboard & Audit Generator

An offline-first field-sales tool built by [The Unorthodox Marketing Agency](https://wearetuma.com) for in-person B2B outreach. Load a leads spreadsheet, browse and filter businesses, and generate branded per-business visibility audits on the spot.

**Live app:** https://[your-github-username].github.io/[repo-name]/

## What it does

- **Load leads** from any Excel or CSV export (the format produced by our scraper)
- **Browse & filter** by location, priority, business type, payment potential, status, and name search
- **Track progress** per lead: New, Visited/Pitched, Interested, Follow-up, No Response, Not Interested, Closed/Won, plus per-lead notes
- **Generate audits** on demand: branded, per-business visibility reports covering website, Google Business Profile, and social/search visibility, with cited statistics from Google, BrightLocal, SCORE, and Harvard Business School
- **Dynamic CTA** in every audit adapts to the issues found (missing website vs. weak GBP vs. no social presence)
- **Download as PDF** to email or hand off after a visit
- **Export the working list** back to Excel with all statuses and notes preserved
- **Multi-list support** via My Lists: keep the GTA, Houston, and any other campaign in the same tool, switch between them freely

## How it works

Everything runs client-side in the browser. Load a spreadsheet, all the data stays on the device (localStorage). No server, no accounts, no analytics, no data leaves the phone or laptop.

- Single self-contained HTML file (~1.9 MB)
- Works offline once loaded
- Optimized for mobile field use (sticky header, thumb-sized buttons, tap-to-call phone numbers, no iOS zoom on inputs)
- Tested on iOS Safari, desktop Chrome/Safari/Firefox

## Deploying with GitHub Pages

Follow these steps to publish the app under your own permanent URL:

1. **Create a new GitHub repo** (public — GitHub Pages needs public repos on free accounts). Name it something like `lead-dashboard`.
2. **Upload the files** in this folder to the repo root (`index.html`, `README.md`, `LICENSE`, `.gitignore`, `.nojekyll`).
3. **Enable Pages:** in your repo, go to **Settings → Pages**. Under "Build and deployment," set Source to **Deploy from a branch**, Branch to **main**, folder to **/ (root)**. Save.
4. **Wait 1-2 minutes.** GitHub will show you the live URL, typically `https://[your-username].github.io/[repo-name]/`.
5. **Open the URL on your phone in Safari** and tap Share → Add to Home Screen. Now it behaves like a native app.

## Updating the app

Any time you change `index.html`, push it to the repo. GitHub Pages redeploys automatically in ~1 minute. Your friend's home screen icon keeps working; they just get the new version on next open.

## Format the app expects

The dashboard reads xlsx or csv files with these columns (produced by our scraper — see `TUMA_Scraper_Houston.zip` or the GTA scraper):

`Company Name, Business Type, Priority, Services Needed, Issues Found (pitch points), Lead Warmth, Lead Score, Payment Potential, Phone, Email, Website, Google Maps, Address, Rating, Reviews, Location, Website Load (s)`

Two more columns are added on export back out: `Status` and `Notes`.

## License

MIT — see LICENSE file.

## Credits

Built for TUMA field sales. Uses [SheetJS](https://sheetjs.com) for spreadsheet parsing and [html2pdf.js](https://github.com/eKoopmans/html2pdf.js) for PDF export (both embedded, no external requests).
