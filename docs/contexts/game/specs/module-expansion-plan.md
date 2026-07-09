# Module Expansion Plan

This is an architecture plan, not an immediate refactor.

## Candidate 1: Scoring Module

Modules: end-game scoring, score rows, grade labels.

Coupling: Reads final game metrics and produces score data plus display labels.

Dependency type: In-process.

Test impact: Replace manual grade checking with boundary tests for final score output.

Recommendation: Safe first extraction because it has few DOM dependencies.

## Candidate 2: Task Router

Modules: `addTask`, `removeTask`, `assign`, `unassign`, `autoTick`, `tasksForTable`, `tableTap`.

Coupling: Shared task list, staff state, table state, priority rules, and DOM badges.

Dependency type: In-process with a DOM adapter later.

Test impact: Boundary tests can verify task creation, assignment, and cleanup without clicking the UI.

Recommendation: Valuable, but only after scoring is separated.

## Candidate 3: Renderer And Input Adapter

Modules: DOM creation, sprite images, drag/drop, hit testing, HUD, badges, overlays.

Coupling: Reads almost every state shape and currently mutates some UI state directly.

Dependency type: Local-substitutable.

Test impact: Browser smoke tests should cover this boundary.

Recommendation: Delay until the game rules are stable.

## Recommended Order

1. Add browser smoke test.
2. Extract scoring.
3. Extract task router.
4. Extract rendering/input adapter.
5. Split CSS only after behavior modules are stable.
