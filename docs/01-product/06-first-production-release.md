# First production release

The founder asked for a **larger first ship** than the original 12-item MVP, **desktop control room first**, with an **interactive map** in that first live-control version.

This file is the scope lock for the first version a real event may use.

Call it **FPR** (first production release), not MVP. It is still not the whole vision.

## FPR must be able to run this day

An organiser can:

1. Create an organisation and invite users.
2. Create an event, pick a type, set dates and timezone.
3. Draw or place a site map with zones and named locations.
4. Put staff into departments and roles.
5. Publish a programme with now / next / later.
6. Sit in a control-room dashboard on a large screen.
7. File a control-log line in a few seconds.
8. Open an incident with ID, category, priority, location, assignment, and a timestamped timeline.
9. Turn an issue into a task and complete it.
10. Message an internal channel and send a priority alert.
11. See weather and fire a threshold alert.
12. Open a written emergency playbook and contacts. The human decides.
13. Keep medical and safeguarding records behind extra permissions.
14. Track vendor/contractor documents by expiry.
15. Issue a basic digital credential with zone access.
16. Clone the event into next year’s draft.
17. Generate a post-event report from live data.
18. Prove who changed what in the audit log.

## In FPR

### Platform

- Organisation
- Users
- Org-level and event-level RBAC
- Audit log
- Staging + production
- MFA for privileged roles

### Event

- Create / edit event
- Dates, build/derig, venue, attendance target and live attendance entry
- Event type + module flags
- Event status
- Clone event (site, zones, roles, playbooks, programme template, vendor list without last year’s incidents)

### Live control (desktop / large screen)

- Live dashboard
- Active / critical incidents
- Open tasks
- Control log stream
- Programme now / next / later
- Staff on site count
- Department status tiles (medical, security, and a generic status)
- Weather tile
- Alerts
- Live map

### Incidents

- All listed categories
- Unique public ID
- Reporter, location, category, priority, description
- Assigned team / person
- Status
- Timestamped actions
- Attachments
- Resolution and closing notes
- Promote from control log

### Control log

- Fast create: time (default now), department, message, action
- Filter and search
- Link to incident

### Tasks

- Assignment, priority, deadline, location, status, comments, attachments, completion time, audit

### Site / map

- Interactive map
- Locations and zones
- Core location types (stages, gates, medical, security, toilets, control, etc.)
- Click location → open related incidents/tasks

### People

- Staff records: role, department, contact, emergency contact, assigned location, shift, check-in/out
- Volunteer records at roster level (not a public application portal)

### Programme

- Stages / areas
- Items with start/end
- Now / next / later
- Visible immediately after save to authorised users

### Communications

- Internal channels by department
- Messages
- Priority messages
- Read receipts

### Weather

- Current conditions from a weather provider
- Event-defined thresholds
- Alerts into the control-room alert stream

### Emergencies

- Playbooks with steps and contacts
- Manual activation (human only)
- Banner on live control when active

### Accreditation / access v1

- Credentials for staff, contractor, vendor, artist, VIP, media, emergency services
- QR payload
- Zone allow-list
- Valid dates and status

### Vendors / contractors v1

- Register
- Documents with expiry (`valid` / `expiring` / `expired` / `missing`)
- Pitch / power notes
- Approval status

### Medical v1 (restricted)

- Medical incidents use the incident model plus medical extras: team, treatment summary, ambulance, hospital transfer, response timestamps
- Extra permission
- Data minimisation: no full clinical record

### Safeguarding v1 (restricted)

- Separate case record, not a normal incident body
- Contacts, escalation, status, audit
- Tight permission
- Not shown on the general incident wall

### Reporting v1

- Generated report: attendance, incident counts, categories, response times, tasks, staff numbers, timeline, lessons-learned field
- Export PDF and CSV where appropriate

## Out of FPR

- Native mobile
- Offline queue
- Voice-to-log
- Public notifications
- AI assistant
- Artist hotels, riders, transport
- Full volunteer application portal
- Gift Aid / payment processing
- Fundraising payment collection (manual totals are enough)
- Parade live tracking of every float GPS
- CCTV
- Logistics slot booking portal for hauliers
- Billing / self-serve SaaS checkout (manual invoicing is allowed)

## Delivery slices inside FPR

Build in this order even though it is one release:

1. Foundation: org, users, RBAC, event, audit
2. Live control shell + control log + incidents + tasks
3. Map + locations + programme
4. Comms + weather + emergencies
5. People + credentials + vendors
6. Medical extras + safeguarding
7. Clone + report
8. Production hardening

Do not start slice 5 until slices 1–3 work on staging with real (non-mocked) records.

## Original 12-item MVP mapping

The original list is all inside FPR:

1. Organisation
2. Event creation
3. Users/RBAC
4. Event dashboard
5. Site/map
6. Incident management
7. Control log
8. Task management
9. Staff/teams
10. Event schedule
11. Basic communications
12. Audit log

FPR adds map interactivity, weather, emergencies, credentials, vendors, medical extras, safeguarding, clone, and report because the first ship was explicitly widened.
