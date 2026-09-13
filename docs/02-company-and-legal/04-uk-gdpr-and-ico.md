# UK GDPR and ICO

Livehelm will process personal data of staff, volunteers, contractors, vendors, and — if modules are on — medical and safeguarding data. Treat UK GDPR as the default operating standard.

## Register with the ICO

Most UK companies processing personal data must pay the ICO data protection fee. Register before production personal data exists.

## Roles

| Situation | Role |
| --- | --- |
| Customer organisation’s event staff data | Customer is controller. Livehelm is processor. |
| Your own billing, website, and support | Livehelm is controller. |
| Subprocessors (Supabase, Vercel, R2, email, Sentry) | Livehelm is processor; they are subprocessors. |

Put this in the customer DPA.

## Lawful bases (starting point)

| Data | Suggested basis | Notes |
| --- | --- | --- |
| Account users | Contract | Needed to provide the service |
| Staff / volunteer records the customer enters | Contract (processor) | Customer’s basis is usually legitimate interests or contract with the person |
| Audit logs | Legitimate interests / legal obligation | Security and evidence |
| Medical extras | Extra condition for health data | Minimise. Customer must have a basis. We still need a DPIA. |
| Safeguarding | Extra sensitive-data conditions | Tight RBAC. DPIA. |

Counsel should review the medical and safeguarding bases before those modules go live.

## Data minimisation

Do not collect:

- date of birth unless a specific check needs it
- NHS numbers
- full clinical notes
- unnecessary photos of casualties
- attendee home addresses for a festival crowd

Attendance is a number. It is not a copy of the ticket database.

## Rights

Build, in FPR or immediately after:

- export of a user’s org-visible data
- a process (even if partly manual) for access, deletion, and correction
- a 30-day internal SLA for requests sent to `privacy@`

Deletion must respect:

- tenant isolation
- audit / legal hold
- “we do not silently rewrite incident history” — close and restrict rather than pretending an incident never existed if a regulator or customer needs the evidence. Counsel should write the retention vs erasure rule.

## Security measures you must actually implement

These are not optional slogans:

- MFA
- RBAC
- TLS in transit
- encryption at rest (Supabase / R2 defaults, confirm settings)
- tenant isolation tests
- audit logs
- backups
- vendor access control

## Breach

If personal data is breached, UK GDPR has a reporting clock. The runbook is [../14-runbooks/04-personal-data-breach.md](../14-runbooks/04-personal-data-breach.md).
