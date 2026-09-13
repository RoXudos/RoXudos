# Control log

The fastest write in the product.

## UI

- Department segmented control (remember last)
- Message (required)
- Action (optional)
- Location typeahead (optional)
- Submit on Cmd/Ctrl+Enter
- Default time = now; “Adjust time” is hidden behind a disclosure

## Server

1. Permission `control_log.create`
2. Mint `LOG-YY-####`
3. Insert + audit
4. Realtime fan-out
5. `mutation_id` accepted

## List

Newest first. Filter by department and search message. Click a line to link / promote.

## Speed budget

A practised operator should submit in under 10 seconds including thinking. If the form needs a scrollbar, it failed.

## Done when

Three lines can be entered in one minute on staging, they persist after refresh, and a second browser sees them appear (once realtime exists; until then, refresh is acceptable for the first day of this file only).
