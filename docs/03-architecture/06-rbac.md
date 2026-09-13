# RBAC

Permissions are granted to **roles**. Roles are assigned to users at **organisation** and/or **event** level.

The effective permission set is the union of org roles and the roles for the current event, minus explicit denials if you later need them. Start with union only.

## Roles (FPR)

| Role | Typical home |
| --- | --- |
| Platform Admin | Livehelm staff |
| Organisation Owner | Org |
| Event Director | Event |
| Event Manager | Event |
| Event Control Manager | Event |
| Control Operator | Event |
| Security Manager | Event |
| Medical Manager | Event |
| Production Manager | Event |
| Volunteer Manager | Event |
| Safeguarding Lead | Event |
| Vendor Manager | Event |
| Staff | Event |
| Volunteer | Event |
| Contractor | Event |
| Vendor | Event |

Custom roles can wait. Extra permissions on a user can wait. Get the named roles right.

## Permission catalogue (FPR starting set)

Use `resource.action` strings.

```text
org.read
org.update
org.billing          # stub; no self-serve billing yet
members.invite
members.role.update
event.create
event.update
event.clone
event.close
dashboard.read
map.read
map.update
location.manage
programme.read
programme.update
control_log.create
control_log.read
incident.create
incident.read
incident.update
incident.close
incident.delete_historical   # almost nobody
task.create
task.read
task.update
comms.read
comms.send
comms.priority
alert.send
weather.read
weather.threshold.manage
emergency.read
emergency.activate
people.read
people.manage
credential.manage
vendor.manage
report.read
report.export
audit.read
medical.read
medical.write
safeguarding.read
safeguarding.write
```

## Role grants (intent)

### Control Operator

Can: create/read/update incidents, create control log, read map, read programme, create/update tasks, send ordinary comms.

Cannot: delete historical incidents, change billing, invite org owners, read safeguarding, read medical extras, activate emergencies unless also granted, manage credentials.

### Event Control Manager

Everything a Control Operator can do, plus emergency activate, programme update, map update, handover report, department status.

### Medical Manager

Medical extras + medical incidents. Not safeguarding by default.

### Safeguarding Lead

Safeguarding cases. Not all medical notes by default.

### Staff / Volunteer / Vendor / Contractor

Read briefing and their tasks. Create a control-log or incident only if you later enable field reporting. In FPR desktop, these roles are mostly records, not logins. Still define the permissions so Phase B does not invent a new model.

### Organisation Owner

Org settings, invites, event create, billing contact. Not automatic medical/safeguarding access.

## Implementation

- Store permissions as a static map in `packages/shared` or `lib/permissions.ts`.
- Enforce on the server.
- Hide nav items in the UI as a convenience only.
- Log denials for restricted modules.

## Checks in FPR

Write automated tests:

- Operator cannot read a safeguarding case
- Owner of org A cannot read org B event
- Medical extras stripped from incident payload without `medical.read`
- Audit exists when a manager reads a safeguarding case
