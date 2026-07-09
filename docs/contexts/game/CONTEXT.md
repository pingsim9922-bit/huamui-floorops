# Game Context

## Ownership

The game context owns the browser game shipped from `index.html`.

## Invariants

- The app must run as a static page with no server-side runtime.
- Vercel deployment must work from the repository root.
- The first screen must be the playable game, not a landing page.
- `newGame()` must create a complete playable state before the first frame.
- `loop()` must tolerate short frame delays and avoid crashing the browser.
- Pointer input must work on both desktop and phone-sized viewports.

## Public Contract

Current public surface:

- Open `index.html` in a browser or serve the root folder.
- Click the start button to begin a session.
- Deploy the root folder to Vercel as a static site.

Future module contract:

- `startGame()` starts a clean session.
- `againGame()` restarts after scoring.
- A single engine tick should advance state without requiring DOM access.
- Rendering should read state and update DOM without changing game rules.

## Current Risk

Most behavior lives in one script and mutates shared state. This is acceptable for the first deployed version, but risky for bigger feature changes.

## Safe Change Policy

Safe now:

- Documentation, deployment config, local scripts.
- Small isolated browser fixes.
- Small text or style fixes after visual verification.

Execute later:

- Extract scoring into a pure module.
- Extract task routing into a module.
- Extract rendering and input into a DOM adapter.

Do not mix:

- UI redesign and game-rule changes in the same change.
- Large refactors and deployment fixes in the same change.
