# Time and IDs

## Time

- Store every timestamp in **UTC**.
- Each event has a `timezone` (IANA), e.g. `Europe/London`.
- Display in the event timezone in control room.
- Control-log times default to “now” and can be back-timed with a reason when radio is late to the desk.
- Show the clock on the live dashboard. Operators glance at it constantly.

## Public IDs

Operators will say IDs over radio.

| Record | Format |
| --- | --- |
| Incident | `INC-26-0142` (year short + per-event sequence) |
| Control log | `LOG-26-0881` |
| Task | `TSK-26-0204` |
| Safeguarding | `SG-26-0011` (never shown on the open wall) |
| Credential | `CRD-26-A91K` |

Keep a UUID primary key internally. Sequence tables are per event so numbers stay small.

Do not reuse sequences after deletes. Cancelled incidents keep their number.

## User-facing dates

Event dates are calendar dates in the event timezone. Build/derig can be date-times.
