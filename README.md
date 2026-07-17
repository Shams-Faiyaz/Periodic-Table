# Interactive Periodic Table (3D) — installable PWA

A self-contained 3D periodic table (Three.js) with all 118 elements, Bohr models,
orbital shapes, periodic-trend heatmaps, phase-at-temperature colouring, themes,
Firebase email sign-in (optional) + guest mode, and full PWA install support.

## Files (upload ALL of them to the repo root — keep them side by side)
- `index.html` — the app
- `manifest.json` — PWA app definition
- `sw.js` — service worker (offline + install)
- `icon-192.png`, `icon-512.png`, `icon-maskable-512.png`, `apple-touch-icon.png`, `favicon.png` — icons

## Publish (GitHub Pages)
1. Repo → **Add file → Upload files** → drag in every file above → **Commit changes**.
2. Repo **Settings → Pages** → Source: *Deploy from a branch* → Branch **main**, folder **/ (root)** → Save.
3. Live at `https://<username>.github.io/<repo>/` after ~1 min.
   Updating later = upload/commit the changed file again.

## Firebase sign-in (optional — guest mode always works)
Config is already in `index.html`. To turn on real sign-in:
1. Firebase Console → **Authentication → Sign-in method** → enable **Email/Password**.
2. Firebase Console → **Authentication → Settings → Authorized domains** → add your live
   domain (e.g. `<username>.github.io`).

## Secure the API key (do this — the key is public by design, so lock it down)
Google Cloud Console → **APIs & Services → Credentials** → the browser key:
- **Application restrictions → Websites**: add `<username>.github.io/*` and `localhost/*`
- **API restrictions → Restrict key**: Identity Toolkit API (+ Token Service API)

A Firebase web API key is safe to ship publicly; restricting it stops others from
reusing it on their own sites. GitHub's secret-scanning alert can be dismissed once restricted.

## Install the app
- **Android (Chrome):** open the site → tap **⬇ Install app** (or ⋮ → Install app).
- **iPhone (Safari):** Share → **Add to Home Screen**.
- **Desktop (Chrome/Edge):** install icon in the address bar, or the **⬇ Install app** button.

Install needs HTTPS (GitHub Pages provides it). Opening the file locally via `file://`
won't install — that's expected.

## Notes
- Keyboard: `1–4` switch views · `R` reset view · `/` search.
- Reset button (↺, bottom-right) recenters/re-zooms the current view; leaves theme/filters/sort.
