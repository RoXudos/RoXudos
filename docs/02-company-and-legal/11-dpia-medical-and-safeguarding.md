# DPIA — medical and safeguarding

Complete a Data Protection Impact Assessment **before** those modules are enabled on a production event.

This file is the skeleton. Fill it with counsel.

## Why a DPIA is required

- Health data and safeguarding case data are high risk
- Wrong access is harmful
- The product may be used under time pressure, which increases misuse risk

## Questions the DPIA must answer

1. What fields exist?
2. Who can see them?
3. How is access audited?
4. What is the retention period?
5. How does erasure interact with incident evidence?
6. What happens if a control operator is over-permissioned?
7. What is the process if a photo of a casualty is uploaded?
8. How do we stop the AI assistant (later) from reading these modules without permission?

## Product rules that the DPIA should lock

- Medical extras are not rendered on the general incident wall beyond category + location + priority + status.
- Safeguarding cases are a separate object, not an incident description that everyone can open.
- Search across the org must not return restricted bodies to unauthorised roles.
- Exports and post-event reports include counts, not narratives, unless the exporter has the restricted permission.
- Attachments inherit the parent record’s sensitivity.

## Go-live gate

Medical / safeguarding toggles stay off in production until:

- [ ] DPIA signed
- [ ] RBAC tests passing
- [ ] Audit on every read of a restricted record (not only writes)
- [ ] Retention job designed
