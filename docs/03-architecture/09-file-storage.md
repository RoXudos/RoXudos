# File storage

## What is stored

- Incident photos
- Task attachments
- Vendor insurance / licences / risk assessments
- Event plan PDFs
- Credential portraits (optional, minimise)
- Report exports (optional cache)

## Bucket layout

```text
org/{organisation_id}/event/{event_id}/incidents/{incident_id}/...
org/{organisation_id}/event/{event_id}/tasks/{task_id}/...
org/{organisation_id}/event/{event_id}/vendors/{vendor_id}/docs/...
org/{organisation_id}/event/{event_id}/plans/...
```

Never put files at a guessable public URL.

## Upload flow

1. Client asks the app for an upload slot.
2. Server checks permission and MIME + size.
3. Server creates a `files` row (`pending`).
4. Server returns a short-lived signed PUT URL.
5. Client uploads.
6. Client confirms. Server marks `ready` and writes audit.

Allowed types for FPR: `image/jpeg`, `image/png`, `image/webp`, `application/pdf`.

Max size: 10 MB per file unless a later decision says otherwise.

## Download flow

Authorisation every time. Signed GET, minutes not days.

Restricted parents require restricted permissions.

## Virus scanning

Add as soon as you accept PDFs from vendors. A ClamAV worker or a commercial scanner. Until then, only authenticated users upload, and you still do not execute files on the server.

## EXIF

Strip location EXIF from photos on upload if the event does not need it. Casualties do not need their home GPS stored because someone’s phone camera attached it.
