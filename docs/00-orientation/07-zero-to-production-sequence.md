# Zero to production — the full sequence

This is the ordered list of work. Each step points at the playbook that explains it. Do not start step 40 because step 12 looks more fun.

## A. Decide and incorporate

1. Read [00-read-this-first.md](00-read-this-first.md).
2. Accept the [decisions log](05-decisions-log.md) or add a dated change.
3. Create the company and bank — [../02-company-and-legal/02-uk-company-setup.md](../02-company-and-legal/02-uk-company-setup.md).
4. Domain, email, password manager — [../02-company-and-legal/03-domain-email-identity.md](../02-company-and-legal/03-domain-email-identity.md).
5. Tick the from-zero legal list through ICO and draft policies — [../02-company-and-legal/01-from-zero-checklist.md](../02-company-and-legal/01-from-zero-checklist.md).

## B. Open vendor accounts

6. Create accounts in the order given — [../07-setup-from-zero/01-accounts-to-create.md](../07-setup-from-zero/01-accounts-to-create.md).
7. Prepare the laptop — [../07-setup-from-zero/02-local-machine.md](../07-setup-from-zero/02-local-machine.md).

## C. Open the real engineering home

8. Create private repo `livehelm` — [../07-setup-from-zero/03-create-product-repo.md](../07-setup-from-zero/03-create-product-repo.md).
9. Copy this bible into that repo — [../07-setup-from-zero/12-copy-docs-into-product-repo.md](../07-setup-from-zero/12-copy-docs-into-product-repo.md).
10. Stop adding product work to the GitHub profile repository.

## D. Slice 0 — a boring app that is hosted

11. Bootstrap Next.js — [../07-setup-from-zero/04-bootstrap-nextjs.md](../07-setup-from-zero/04-bootstrap-nextjs.md).
12. Local + staging + production Supabase — [../07-setup-from-zero/05-supabase-projects.md](../07-setup-from-zero/05-supabase-projects.md).
13. Cloudflare DNS + R2 — [../07-setup-from-zero/06-cloudflare-and-r2.md](../07-setup-from-zero/06-cloudflare-and-r2.md).
14. Vercel environments — [../07-setup-from-zero/07-vercel-environments.md](../07-setup-from-zero/07-vercel-environments.md).
15. Email, Sentry, uptime — [../07-setup-from-zero/08-email-errors-uptime.md](../07-setup-from-zero/08-email-errors-uptime.md).
16. Env names only as specified — [../07-setup-from-zero/09-env-and-secrets.md](../07-setup-from-zero/09-env-and-secrets.md).
17. CI — [../07-setup-from-zero/10-ci.md](../07-setup-from-zero/10-ci.md).
18. Health + sign-in deployed — [../07-setup-from-zero/11-health-and-home.md](../07-setup-from-zero/11-health-and-home.md).

## E. Slice 1 — foundation

19. Schema + RLS — [../08-build-foundation/01-schema-and-rls.md](../08-build-foundation/01-schema-and-rls.md).
20. Permissions engine — [../08-build-foundation/02-permissions-engine.md](../08-build-foundation/02-permissions-engine.md).
21. Audit writer — [../08-build-foundation/03-audit-writer.md](../08-build-foundation/03-audit-writer.md).
22. Org + invite — [../08-build-foundation/04-org-and-invite.md](../08-build-foundation/04-org-and-invite.md).
23. Event create — [../08-build-foundation/05-event-create.md](../08-build-foundation/05-event-create.md).
24. Event roles — [../08-build-foundation/06-event-membership-roles.md](../08-build-foundation/06-event-membership-roles.md).
25. App shell — [../08-build-foundation/07-app-shell.md](../08-build-foundation/07-app-shell.md).
26. Event settings — [../08-build-foundation/08-event-home.md](../08-build-foundation/08-event-home.md).
27. MFA gate — [../08-build-foundation/09-mfa-privileged.md](../08-build-foundation/09-mfa-privileged.md).
28. Cross-tenant tests — [../08-build-foundation/10-cross-tenant-tests.md](../08-build-foundation/10-cross-tenant-tests.md).
29. Pass the [slice 1 gate](../08-build-foundation/11-slice-1-done.md).

## F. Slices 2–4 — live control

30. Live shell — [../09-build-live-control/01-live-shell.md](../09-build-live-control/01-live-shell.md).
31. Control log — [../09-build-live-control/02-control-log.md](../09-build-live-control/02-control-log.md).
32. Incidents — [../09-build-live-control/03-incidents.md](../09-build-live-control/03-incidents.md).
33. Promote log — [../09-build-live-control/04-promote-log-to-incident.md](../09-build-live-control/04-promote-log-to-incident.md).
34. Tasks — [../09-build-live-control/05-tasks.md](../09-build-live-control/05-tasks.md).
35. Locations — [../09-build-live-control/06-locations-list.md](../09-build-live-control/06-locations-list.md).
36. Interactive map — [../09-build-live-control/07-interactive-map.md](../09-build-live-control/07-interactive-map.md).
37. Programme — [../09-build-live-control/08-programme.md](../09-build-live-control/08-programme.md).
38. Realtime — [../09-build-live-control/09-realtime.md](../09-build-live-control/09-realtime.md).
39. Comms + alerts — [../09-build-live-control/10-comms-and-alerts.md](../09-build-live-control/10-comms-and-alerts.md).
40. Weather — [../09-build-live-control/11-weather.md](../09-build-live-control/11-weather.md).
41. Emergencies — [../09-build-live-control/12-emergencies.md](../09-build-live-control/12-emergencies.md).
42. Attendance + department status — [../09-build-live-control/13-attendance-and-status.md](../09-build-live-control/13-attendance-and-status.md).
43. Pass the [slices 2–4 gate](../09-build-live-control/14-slice-2-4-done.md).

## G. Slices 5–7 — extras the first ship still needs

44. People and shifts — [../10-build-first-ship-extras/01-people-and-shifts.md](../10-build-first-ship-extras/01-people-and-shifts.md).
45. Check in/out — [../10-build-first-ship-extras/02-check-in-out.md](../10-build-first-ship-extras/02-check-in-out.md).
46. Credentials — [../10-build-first-ship-extras/03-credentials.md](../10-build-first-ship-extras/03-credentials.md).
47. Vendors — [../10-build-first-ship-extras/04-vendors-and-documents.md](../10-build-first-ship-extras/04-vendors-and-documents.md).
48. Finish DPIA, then medical extras — [../10-build-first-ship-extras/05-medical-extras.md](../10-build-first-ship-extras/05-medical-extras.md).
49. Safeguarding — [../10-build-first-ship-extras/06-safeguarding.md](../10-build-first-ship-extras/06-safeguarding.md).
50. Plans library — [../10-build-first-ship-extras/07-plans-library.md](../10-build-first-ship-extras/07-plans-library.md).
51. Clone — [../10-build-first-ship-extras/08-clone-event.md](../10-build-first-ship-extras/08-clone-event.md).
52. Report — [../10-build-first-ship-extras/09-post-event-report.md](../10-build-first-ship-extras/09-post-event-report.md).
53. Close event — [../10-build-first-ship-extras/10-close-event.md](../10-build-first-ship-extras/10-close-event.md).
54. Charity manual totals if needed — [../10-build-first-ship-extras/11-fundraising-manual.md](../10-build-first-ship-extras/11-fundraising-manual.md).
55. Pass the [slices 5–7 gate](../10-build-first-ship-extras/12-slice-5-7-done.md).

## H. Prove it, then go live

56. Tests as specified in [../13-testing/README.md](../13-testing/README.md).
57. Pre-production checklist — [../12-production/01-pre-production-checklist.md](../12-production/01-pre-production-checklist.md).
58. Restore drill — [../12-production/03-backups.md](../12-production/03-backups.md).
59. Staging rehearsal — [../12-production/02-staging-rehearsal.md](../12-production/02-staging-rehearsal.md).
60. First real event — [../12-production/05-go-live.md](../12-production/05-go-live.md).
61. Keep [runbooks](../14-runbooks/README.md) open during that event.

## I. After the first real event

62. Debrief with the success metrics file.
63. Harden — [../12-production/08-hardening.md](../12-production/08-hardening.md).
64. Only then open [../11-later-phases/README.md](../11-later-phases/README.md) (mobile, offline, Pride depth, AI).
