# Esports Bracket Predictor V2.0

A local-first, installable esports tournament bracket and prediction app. No build step, backend, API key, or external dependency is required.

## Features
- Create tournaments for 4, 8, 16, or 32 teams; register and remove teams before bracket generation.
- Randomized single-elimination bracket with byes for unfilled slots.
- Elo-based win probabilities, adjustable team ratings, deterministic prediction view, and randomized upset simulation.
- Record and undo official match winners; downstream results are cleared when an upstream result changes.
- Personal picks and round-weighted prediction leaderboard (2^round points).
- JSON backup and validated restore, including teams, bracket, results, ratings, and picks.
- Demo tournament with seeded teams, ratings, results, and sample leaderboard entries.
- Responsive layout, offline service-worker cache, web app manifest, 192/512/maskable icons, and install prompt.

## Deploy to GitHub Pages
1. Create a GitHub repository and upload the contents of this folder to the repository root (so `index.html` is at the root).
2. Open **Settings → Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**, select your deployment branch (usually `main`) and folder `/ (root)`, then save.
4. Wait for the Pages deployment to finish and open the published URL.
5. Open the site over HTTPS and use **Install app** when your browser offers it. On iOS, use Share → Add to Home Screen.

If deploying to a project subpath, keep all files together and do not change the relative `./` asset paths.

## Data and privacy
Tournament data is stored in the browser's local storage on the device/profile in use. It is not automatically synchronized between devices or shared with other players. Use **Backup** to export a JSON file and **Restore** to move a tournament to another browser/device. Do not clear browser storage unless you have a backup.

## Local preview
Serve this folder with any static HTTP server (for example `python -m http.server 8000`) and open `http://localhost:8000`. Service workers and PWA installation require localhost or HTTPS; opening `index.html` directly still allows the core app to run but not install/offline-cache.

## Validation performed
- ZIP structure and required PWA assets checked.
- HTML/JS syntax checked with Node.js when available.
- Backup schema and deployment paths reviewed.
