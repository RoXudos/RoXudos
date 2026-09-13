# Live shell

## Steps

1. Route `/app/events/[eventId]/live`.
2. Permission `dashboard.read`.
3. Implement the mosaic from [../05-design/03-control-room-ui.md](../05-design/03-control-room-ui.md).
4. Tiles can show `—` until their module exists. Do not invent numbers.
5. Quick log composer is the first interactive widget (next file).
6. Large-screen CSS first, then collapse columns.

## Empty

If the event has no locations, incidents, or programme, the mosaic still renders with honest empties.

## Done when

A Control Operator can open Live on a 1920px screen and see the clock, status pill, and empty tiles. No placeholder “8,421” attendance.
