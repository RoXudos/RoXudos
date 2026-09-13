# Realtime control room

The dashboard must update without a full page refresh.

## What is realtime in FPR

- New control-log lines
- Incident create / status / assignment
- Task status
- Programme item changes
- Alerts
- Emergency activation banner
- Attendance / staff-on-site numbers when they change

## What can stay request/response

- Org settings
- Vendor document uploads
- Audit log viewer
- Report generation

## Channel design

One Supabase realtime channel per event:

```text
event:{event_id}
```

Clients subscribe only after the server has confirmed the user may `dashboard.read` on that event.

Do not make a global “all organisations” channel.

## Payload rules

Realtime events should carry IDs and small summaries, not medical notes or safeguarding bodies.

If a restricted field changes, send `incident.updated` with `id` and `sensitivity: medical`. Clients without permission refetch a redacted resource.

## Failure

If the socket drops:

- show a visible “live link degraded — reconnecting”
- poll every 15 seconds as fallback
- never show stale criticals as if they were live without a last-updated time

## Fan-out volume

A control room has tens of users, not millions. Do not invent Kafka.
