# Promote log to incident

## Steps

1. On a log line, action “Create incident”.
2. Prefill summary from message, location, department → suggested category.
3. Creating the incident sets `promoted_from_log_id` and `incidents.incident_id` on the log line.
4. The log line stays. It is not deleted.

## Done when

Radio-style logging stays fast, and a fight at Gate 3 can become `INC-26-0142` without retyping.
