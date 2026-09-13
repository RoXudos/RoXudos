# Information architecture

## Signed-out

- Sign in
- Invite accept
- Password reset

No public marketing app inside the product repo required for FPR.

## Organisation level

- Events list
- People (org directory)
- Organisation settings
- Roles
- Audit (org-wide)
- Billing contact (manual)

## Event level — primary nav

Order matters. This is the control product.

1. **Live** (dashboard)
2. **Log**
3. **Incidents**
4. **Tasks**
5. **Map**
6. **Programme**
7. **People**
8. **Comms**
9. **More** → Weather, Emergencies, Vendors, Credentials, Plans, Reports, Settings, Audit

Restricted:

- **Medical** (if permitted)
- **Safeguarding** (if permitted)

Those two are not buried inside Incidents as open tabs for everyone.

## Global chrome

- Event name + status pill (`LIVE`)
- Clock in event timezone
- Alert bell
- User menu
- Quick add: Log / Incident / Task

## URLs

```text
/app                                org events
/app/events/[eventId]/live
/app/events/[eventId]/log
/app/events/[eventId]/incidents
/app/events/[eventId]/incidents/[id]
/app/events/[eventId]/tasks
/app/events/[eventId]/map
/app/events/[eventId]/programme
/app/events/[eventId]/people
/app/events/[eventId]/comms
/app/events/[eventId]/weather
/app/events/[eventId]/emergencies
/app/events/[eventId]/vendors
/app/events/[eventId]/credentials
/app/events/[eventId]/safeguarding
/app/events/[eventId]/reports
/app/events/[eventId]/settings
/app/events/[eventId]/audit
```
