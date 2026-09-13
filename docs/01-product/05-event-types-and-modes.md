# Event types and modes

When an organiser creates an event they select a type. The type does not fork the codebase. It sets **module flags**.

## Types

- Festival
- Pride
- Charity
- Parade
- Mass participation
- Community
- Christmas market
- Fireworks
- Concert
- Sport
- Corporate
- University
- Carnival
- Cultural
- Other

Pride and Parade are separate because a Pride event may include a parade, stages, and a village. A parade-only civic event may not need Pride-specific copy.

An event may enable extra modules manually. Type is a preset, not a prison.

## Presets

### Always on

- Event record
- Users and event RBAC
- Live dashboard
- Incidents
- Control log
- Tasks
- Staff / teams
- Programme
- Site / map
- Communications
- Audit
- Weather
- Emergency playbooks

### Festival / concert extra on by default

- Artists / running order extras
- Vendors
- Accreditation
- Production-friendly location types
- Crowd and noise incident categories already exist in the core

### Pride extra on by default

- Parade route and groups
- Accessibility planning fields
- Road closures / diversions as map layers
- Volunteer-heavy staffing
- Safeguarding on

### Charity extra on by default

- Fundraising summary
- Participants (simple register)
- Volunteers
- Sponsors
- Safeguarding on
- Registration count

### Parade extra on by default

- Route
- Assembly
- Group order
- Closures
- Stewards / marshals

### Mass participation extra on by default

- Course / route
- Start waves
- Medical density
- Participants
- Lost person / welfare categories emphasised

### Community / cultural / Christmas / carnival / fireworks / sport / corporate / university

Start from the always-on set. Add vendors, accreditation, route, or fundraising only if the organiser turns them on.

Fireworks should default weather and emergency playbooks to highly visible.

## Implementation rule

```text
event_type → default module_flags[]
organiser may toggle flags later
UI hides navigation for flags that are off
APIs still enforce permission if someone calls a disabled module
```

Do not create `PrideIncident` or `FestivalTask` tables. Use the same tables. Add nullable module-specific fields or child tables.
