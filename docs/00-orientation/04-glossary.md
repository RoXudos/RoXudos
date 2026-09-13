# Glossary

Use these words in the product and in these docs. Do not invent a second vocabulary.

| Term | Meaning |
| --- | --- |
| Organisation | The tenant. A company, council, charity, university, or promoter. Owns many events. |
| Event | A single operational event, including build and derig dates. |
| Event type | Festival, Pride, charity, parade, and the other types. Turns modules on or off. |
| Site | The physical place the event occupies. An event can have more than one site. |
| Zone | An access or operational area on a site. Credentials grant zone access. |
| Location | A named point or area used on incidents, tasks, and the map. |
| Live control | The desktop control-room experience. The centre of the product. |
| Control log | Fast timestamped operational record. Not the same as an incident. |
| Incident | A managed operational event with a unique ID, status, timeline, and assignment. |
| Action | A timestamped thing that happened on an incident or log entry. |
| Task | Work that must be done. Anything operational can become a task. |
| Programme | Running order. Now / next / later. |
| Briefing | Information a person must see before or during a shift. |
| Credential | Digital pass for a person or organisation. Later shown as QR. |
| Control operator | Role that can create and update live operational records, but cannot administer the organisation. |
| Sensitive module | Medical, safeguarding, and some security records. Extra permission required. |
| Audit log | Immutable record of who changed what, when, on which event and record. |
| Correction | A new timestamped entry that amends history. History is not rewritten. |
| First production release | The first version a real event is allowed to use. Wider than a demo MVP. |
| Field mobile | Later phone experience for staff on site. Not in the first production release. |
| Offline queue | Later local store for unsent records. Never shown as synced unless it is. |
| AI assistant | Later read-only helper over authorised data. Never an incident or emergency decision-maker. |
| Purple Guide | UK outdoor events guidance. Useful practice, not a product feature name. |
| DPIA | Data Protection Impact Assessment. Required before medical/safeguarding modules go live. |
| DPA | Data Processing Agreement with a processor. |
| SCC | Standard Contractual Clauses for some international transfers. |
| Tenant isolation | One organisation must never see another organisation’s data. |

## Incident is not a control-log entry

A control-log line can be written in seconds:

> 14:21 SECURITY — Fight at Gate 3. Action: Security dispatched.

That line can later be **promoted** to an incident if it needs assignment, a timeline, attachments, and a close-out.

Do not force every radio message through a 20-field incident form.

## Status words

Use these status families unless a module file says otherwise:

- Event: `draft`, `planned`, `build`, `live`, `closed`, `archived`
- Incident: `new`, `acknowledged`, `dispatched`, `on_scene`, `escalated`, `closed`, `cancelled`
- Task: `open`, `in_progress`, `blocked`, `done`, `cancelled`
- Credential: `draft`, `active`, `suspended`, `expired`, `revoked`
- Document: `valid`, `expiring`, `expired`, `missing`

## Priority words

Use `low`, `medium`, `high`, `critical`.

Show them as words, not only colour. Colour-blind users and large screens both need the word.
