# Definition of done

A feature is not done when the happy path renders once.

## Every user-facing feature

- [ ] Permission checked on the server, not only hidden in the UI
- [ ] Unauthorised users get a safe empty or forbidden state, never another tenant’s data
- [ ] Audit entry written for create, update, assign, status change, close, export, and permission change
- [ ] Loading state
- [ ] Empty state with a next action
- [ ] Error state that a control operator can understand
- [ ] Keyboard and screen-reader usable
- [ ] Works at 1280px and on a large control-room width
- [ ] No unexplained TODO
- [ ] No mocked operational data left in the path

## Every data change

- [ ] Tenant (`organisation_id`) set in the database, not only in the app
- [ ] RLS policy covers the table
- [ ] Validation on the server
- [ ] Timestamps in UTC, displayed in the event timezone
- [ ] IDs are unique and human-usable where operators must read them aloud (`INC-2026-0142`, not only a UUID)

## Every first-production module

- [ ] Playbook steps completed
- [ ] Seed data can demonstrate the module without pretending to be a live event
- [ ] Tests listed in `13-testing` for that module are written and passing
- [ ] Sensitive fields are listed and permissioned
- [ ] Export / report path does not leak restricted modules

## A release may go to a real event only when

- [ ] Staging has been used as if it were live
- [ ] Backups have been restored once
- [ ] MFA is required for control, medical, safeguarding, and org-admin roles
- [ ] DPIA exists for medical and safeguarding if those modules are on
- [ ] Processor list and DPAs exist
- [ ] Support / escalation contact is written down
- [ ] A handover report can be generated from real data
- [ ] Someone who did not build the feature can create an incident and a control-log line without training beyond a one-page briefing
