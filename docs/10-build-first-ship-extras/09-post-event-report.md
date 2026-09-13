# Post-event report

## Steps

1. Button on `/reports` for permitted roles.
2. Run queries listed in the data-model reporting file.
3. Store jsonb payload + optional PDF.
4. Lessons-learned textarea.
5. CSV export of incident list (redacted by permission).

## Done when

Closing an event with 10 incidents produces a report whose counts match the live lists. Editing an incident after generation does not silently change the stored snapshot; “regenerate” is explicit.
