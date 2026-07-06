# Guandan Rules

A single-page, installable reference for the rules of **Guandan** (掼蛋), the Chinese partnership card game — covering setup, card ranking, legal combinations, tribute, trick-play, and scoring.

Live demo (after Pages is enabled): `https://<your-username>.github.io/<repo-name>/`

## Files

| File | Purpose |
|---|---|
| `index.html` | The full rules reference — single self-contained page (HTML/CSS/JS inline). |
| `manifest.json` | Web app manifest so the site can be installed as a standalone app. |
| `icon-192.png`, `icon-512.png` | App icons used by the manifest. |
| `apple-touch-icon.png` | Home screen icon for iOS. |
| `favicon-32.png` | Browser tab favicon. |

## Setup

1. Push all files above into the same folder (repo root or a subfolder — just keep them together, since they reference each other by relative path).
2. In the repo, go to **Settings → Pages**, and set the source to the branch/folder containing these files.
3. GitHub will publish the site at `https://<your-username>.github.io/<repo-name>/`.

## Installing on iPhone

1. Open the published URL in **Safari**.
2. Tap the **Share** icon.
3. Tap **Add to Home Screen**.

The page will open full-screen, without Safari's address bar, using its own icon — like a native app.

## Editing

The whole site is one HTML file with inline CSS and JS — no build step, no dependencies. Open `index.html` in any editor, change the content or styles, and refresh the browser (or re-deploy via Pages) to see updates.
