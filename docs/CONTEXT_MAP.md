# Context Map

This repository is a static browser game. The live product is currently one file, but the domain already has clear bounded contexts.

## Contexts

1. Game Session
   Owns time, score, revenue, stars, end-game grade, and the running/stopped lifecycle.

2. Floor Operations
   Owns tables, waiting groups, seating, eating, payment, table turnover, yellow orders, complaints, and customer patience.

3. Staff Operations
   Owns staff position, stamina, current task, drag/drop assignment, auto-assignment, station duty, chatting, and rush/calm skills.

4. Kitchen And Bar
   Owns food/drink preparation queues, station capacity, delivery tasks, dirty plates, dirty cups, and washing bottlenecks.

5. Rendering And Input
   Owns DOM creation, sprite generation, drag hit testing, HUD refresh, map labels, badges, overlays, and pointer events.

## Current Coupling

The contexts are implemented together in `index.html`. Most functions read or mutate the shared `G` object directly. That makes the game easy to ship as a static page, but harder to test or safely expand.

## Desired Direction

Keep `index.html` as the deployed shell until the game is stable. When the project grows, split by deep modules with small public interfaces:

- `GameEngine`: session lifecycle and tick orchestration.
- `TaskRouter`: task creation, assignment, priority, and cleanup.
- `FloorModel`: customers, tables, queues, and state transitions.
- `Renderer`: DOM-only rendering and pointer input.
- `Scoring`: end-game grade and metric calculation.
