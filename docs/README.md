# Livehelm — Project Bible

Working name: **Livehelm**  
Promise: **Plan. Control. Respond. Deliver.**  
What this is: one operational platform for planning, controlling, running, and reviewing live events.

This folder is the project bible. It is written so a founder, a future developer, a hired team, or an AI coding agent can take the product from zero to production without inventing a second plan.

If you only read four files, read these:

1. [00-orientation/00-read-this-first.md](00-orientation/00-read-this-first.md)
2. [00-orientation/02-repo-and-workspace-recommendation.md](00-orientation/02-repo-and-workspace-recommendation.md)
3. [03-architecture/01-recommended-stack.md](03-architecture/01-recommended-stack.md)
4. [01-product/06-first-production-release.md](01-product/06-first-production-release.md)

Then follow the numbered folders in order.

---

## How these docs were decided

These files follow the founder brief plus the answers below.

| Decision | Choice |
| --- | --- |
| Audience | Project bible for founder, future developers, and a hired team |
| Structure | Master index plus deep phase folders |
| This GitHub repo | Temporary home only. Do not build the product in the GitHub profile repo. Create a dedicated product repo before writing application code. |
| Stack | Recommended in these docs. Do not pick a second stack unless a later decision log says why. |
| Who implements | Unknown. Every playbook is written so a solo founder, an AI agent, or a team can follow it. |
| Hosting | Simplest UK/GDPR-friendly path that is still production-grade |
| Year-one infrastructure | Production-grade from day one: staging, backups, monitoring, DPAs, support contacts |
| First ship | Wider than a skinny MVP. Desktop live control room plus interactive map plus the modules needed to run a real event |
| Mobile | Control-room desktop first. Field mobile comes after first production |
| Maps | Interactive site map in the first live-control version |
| Event types | Generic platform. Event type only turns modules on or off |
| Market | UK + EU + US from the start, with EU/UK as the primary data region |
| Company / accounts | Start from zero. These docs include company, domain, email, legal, and vendor setup |
| Product name | Working name **Livehelm** until a real name is chosen |

---

## Folder map

| Folder | What it contains |
| --- | --- |
| [00-orientation](00-orientation/README.md) | How to use the bible, glossary, decisions, repo recommendation |
| [01-product](01-product/README.md) | Vision, users, lifecycle, first production release, roadmap |
| [02-company-and-legal](02-company-and-legal/README.md) | Company, domain, UK/EU/US privacy, contracts, insurance |
| [03-architecture](03-architecture/README.md) | Stack, tenancy, RBAC, realtime, maps, environments |
| [04-security](04-security/README.md) | Auth, isolation, sensitive modules, audit, appsec |
| [05-design](05-design/README.md) | UX principles, control-room UI, tokens, accessibility |
| [06-data-model](06-data-model/README.md) | Entities, IDs, statuses, audit fields |
| [07-setup-from-zero](07-setup-from-zero/README.md) | Accounts, tools, repo bootstrap, environments |
| [08-build-foundation](08-build-foundation/README.md) | Org, users, events, RBAC, audit |
| [09-build-live-control](09-build-live-control/README.md) | Dashboard, incidents, control log, tasks, map, programme, comms |
| [10-build-first-ship-extras](10-build-first-ship-extras/README.md) | Weather, emergencies, people, credentials, vendors, medical, safeguarding, reports |
| [11-later-phases](11-later-phases/README.md) | Mobile, offline, Pride/charity modes, artists, logistics, AI |
| [12-production](12-production/README.md) | Hardening, launch, backups, monitoring, support |
| [13-testing](13-testing/README.md) | What to test before a live event uses the system |
| [14-runbooks](14-runbooks/README.md) | Day-of-event and production operations |

---

## Suggested reading order

### Week 0 — decide and set up the company

1. Orientation
2. Product vision and first production release
3. Company and legal from-zero checklist
4. Recommended stack
5. Create the dedicated product repo and vendor accounts

### Week 1+ — build foundation

6. Design principles
7. Data model
8. Setup-from-zero playbooks
9. Foundation build playbooks

### Then — build the differentiator

10. Live control room playbooks
11. First-ship extras
12. Testing
13. Production launch
14. Later phases only after a real event has used the first ship

---

## Rules that apply to every later file

1. Do not replace this architecture without a written decision.
2. Do not fake live operational data with static mocks in production code.
3. Do not let AI make emergency decisions.
4. Do not expose medical, safeguarding, or security-sensitive records without a specific permission.
5. Do not silently edit operational history. Corrections are new timestamped entries.
6. Do not put application code in the GitHub profile repository.
7. If a step needs a human decision, say so. Do not hide it behind automation.

---

## Status of this bible

These files are the implementation plan and operating manual. They are not the product yet. The current GitHub repository only contains this documentation.
