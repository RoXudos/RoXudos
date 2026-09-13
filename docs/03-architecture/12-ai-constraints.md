# AI constraints

AI is **not** in the first production release.

When it is added, these rules are already true:

1. The model only sees data the current user can already see.
2. Restricted modules are excluded unless the user has that permission **and** the prompt is inside that module.
3. The model must not create, close, assign, or escalate incidents unless a human confirms each action. Default is read-only.
4. The model must not activate emergencies.
5. Answers must separate **facts from the system** and **suggestions**.
6. If the data is missing, say so. Do not invent an incident.
7. Prompts and completions that include personal data stay in the EU/UK or are not sent to a US model without a transfer decision.
8. Every AI answer that is used operationally should be storeable on the handover, with model + time + user.

Recommended first AI jobs, later:

- “Summarise open incidents for handover”
- “List outstanding high tasks”
- “What happened at Main Stage between 14:00 and 16:00?” (from log + incidents)

Not:

- “Should we evacuate?”
- “Auto-dispatch medical”
