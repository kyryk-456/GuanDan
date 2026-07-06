# Guandan Rules

A single-page, installable, bilingual reference for the rules of **Guandan** (掼蛋), the Chinese partnership card game — plus a live game tracker for keeping score at the table.

Live demo (once Pages is enabled): `https://<your-username>.github.io/<repo-name>/`

## Features

- **Two top-level pages, switchable from a bar under the header:**
  - **Rules** — a continuous-scroll reference with its own sticky sub-nav (Overview, Dealing, Ranking, Combos, Tribute, Playing, Scoring).
  - **Tracker** — a standalone page for live games: editable team names, tap-or-step level trackers for each team, and a separate tracker for the level the current hand is being played at. Progress saves automatically in the browser's local storage, so it's still there next time you open the app on the same device (it won't sync across devices).
- **Bilingual (English / 简体中文)** — a toggle in the top-right corner of the header swaps every string on the page instantly, including inside the Tracker. The choice is remembered on the device.
- **Installable as a home-screen app** on iPhone/Android via the web app manifest and icons — opens full-screen, no browser chrome.

## Rules content covered

1. **Overview** — setup, deck, players, goal
2. **Dealing & Seating** — self-drawing (no dealer), counter-clockwise direction, how the first hand's leader is determined, how shuffle/cut/draw duties rotate hand to hand, tribute-based lead assignment, and the "welcome back" (接风) rule
3. **Ranking** — standard card order, the level card, and the Hearts-suit true wildcard (逢人配)
4. **Combos** — all legal play shapes, including bombs, joker bomb, and the straight flush bomb tier
5. **Tribute** — the pre-hand tribute/anti-tribute flow
6. **Playing a Hand** — lead, respond, trick resolution, finishing, hand end
7. **Scoring** — level advancement by finishing order, and the distinct requirement for actually clearing Ace level (1st+2nd or 1st+3rd only)

## Files

| File | Purpose |
|---|---|
| `index.html` | The entire site — single self-contained page (HTML/CSS/JS inline, no build step, no external JS dependencies). |
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

The whole site is one HTML file with inline CSS and JS — no build step, no dependencies. Open `index.html` in any editor and look for:

- `<div id="page-rules">` / `<div id="page-tracker">` — the two top-level pages.
- `<section id="...">` — each rules section; add a new one and a matching `<a href="#...">` in `nav.tabs` to extend the reference.
- `const ZH = { ... }` (near the bottom, in the `<script>` block) — the Chinese translation dictionary. Every element with a `data-i18n="key"` attribute needs a matching `'key': '...'` entry here; the English text lives directly in the HTML itself.
- `LEVELS` / `STORAGE_KEY` in the tracker script — the level list and the local-storage key used by the Tracker page.

After editing, refresh the browser (or re-deploy via Pages) to see updates.
