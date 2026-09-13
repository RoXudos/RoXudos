# Emergencies

## Steps

1. Seed playbooks per event from global templates (fire, evacuation, severe weather, major medical, missing child, security threat, structural, power).
2. Event Control Manager can edit steps and contacts.
3. Activate requires `emergency.activate` + re-auth confirm (“Type the event name”).
4. Activation writes audit, alert, banner on Live.
5. Stand-down is a second explicit action.
6. No AI. No automatic activate from weather.

## Done when

Activating “Missing child” shows the procedure and contacts on authorised screens and a red banner on Live. A Control Operator cannot activate it.
