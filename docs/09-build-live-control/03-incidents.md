# Incidents

## Create

Fields:

- Category (required)
- Priority (required, default medium)
- Location (typeahead or text)
- Summary (required, short)
- Description (optional)
- Reporter (default current user name)
- Assigned team / person (optional)

Time reported defaults to now.

Do not put medical extras on this form. If category is medical, create the incident, then a Medical Manager fills extras on a second panel.

## Detail

- Public ID large
- Status control
- Timestamped action list
- “Add action” with kind + body
- Attachments
- Close: resolution + notes required
- Create task
- Restricted banner if `sensitivity !== normal`

## Status transitions

```text
new → acknowledged → dispatched → on_scene → closed
                 ↘ escalated ↗
any → cancelled (reason required)
```

Each transition writes an `incident_action` and audit.

## List + Live tile

Active = not closed/cancelled. Critical tile = priority critical and active.

## Done when

The example timeline in the founder brief can be reproduced as actions, not as one paragraph.
