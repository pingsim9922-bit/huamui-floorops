# Hua Mui Flow Master

Restaurant floor-ops simulation game for Hua Mui Kopitiam.

The current app is a pure static site:

- `index.html` contains the full UI, styles, sprites, and game logic.
- `vercel.json` enables clean static URLs on Vercel.
- No build step is required.

## Run Locally

```powershell
npm run dev
```

Then open:

```text
http://127.0.0.1:4173
```

## Deploy

The GitHub remote is:

```text
https://github.com/pingsim9922-bit/huamui-floorops.git
```

Vercel can deploy the repository directly as a static project. Use these settings:

- Framework preset: Other
- Build command: empty
- Output directory: empty / project root

## Project Shape

This repo intentionally keeps the production app as a single static page for now. The architecture notes in `docs/` explain where to split the code later without changing gameplay behavior.

Safe to execute now:

- Keep the shipped game as `index.html`.
- Add documentation, local run scripts, and deployment notes.
- Fix small browser/runtime errors.

Execute later:

- Split game state, task routing, rendering, scoring, and input handling into modules.
- Add automated browser smoke tests.

Do not execute without a backup branch:

- Large behavior refactors inside the live `index.html`.
- Rewriting drag/drop, auto-assignment, or scoring while also changing UI.
