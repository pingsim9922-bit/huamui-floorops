# Ubiquitous Language

Use these terms consistently in code, issues, and future docs.

## Core Terms

- Group: A customer party moving through waiting, seating, ordering, eating, paying, and leaving.
- Table: One dining table with states such as ready, reserved, occupied, dirty, or flow.
- Staff: A worker pawn with stamina, speed, current task, and optional station duty.
- Task: A unit of work that staff can perform, such as seating, delivery, complaint handling, washing, or flow step.
- Station: A fixed operating point such as Kitchen, Bar, Cleaning, Cashier, Host, Waiting, or Entrance.
- Flow: The table-turnover sequence after guests leave.
- Yellow Order: A late order that needs attention before satisfaction drops.
- Complaint: A high-priority customer problem.
- Preclear: Optional early clearing before a table is fully finished.
- Rush: Temporary staff speed boost with stamina cost.

## Code Names

- `G`: Global game state.
- `CFG`: Tunable gameplay configuration.
- `POS`: Named map coordinates.
- `STAFF_DEF`: Staff roster definition.
- `TABLE_TASK_PRIO`: Priority map for table-related tasks.
