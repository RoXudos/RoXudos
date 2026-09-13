# How to use these docs

These files are a project bible, not a blog and not a slide deck.

## If you are the founder

1. Read [00-read-this-first.md](00-read-this-first.md) and [03-working-name-and-positioning.md](03-working-name-and-positioning.md).
2. Complete [../02-company-and-legal/01-from-zero-checklist.md](../02-company-and-legal/01-from-zero-checklist.md).
3. Create the dedicated product repository described in [02-repo-and-workspace-recommendation.md](02-repo-and-workspace-recommendation.md).
4. Do not skip legal and vendor DPAs because they feel slower than coding.
5. When you ask an AI agent to implement something, point it at the relevant playbook and the decisions log. Tell it not to invent a second architecture.

## If you are a developer or AI coding agent

1. Read the orientation folder and the recommended stack before touching code.
2. Treat [../00-orientation/05-decisions-log.md](05-decisions-log.md) as binding.
3. Implement one playbook at a time.
4. Reuse existing patterns. Do not create a second button component, a second permission helper, or a second audit writer.
5. Every feature must consider: permission, audit, empty state, loading state, error state, desktop usability, and sensitive-data rules.
6. Do not leave unexplained TODOs.
7. Do not replace working architecture without a written decision.

## If you are an agency or hired team

1. Use this bible as the scope baseline.
2. Quote and schedule against the first production release, not the full vision.
3. If you want to change stack, hosting, or tenancy, write a decision-log entry and get founder approval first.
4. Deliver in the same order as folders `07` → `12`.
5. The acceptance bar is [06-definition-of-done.md](06-definition-of-done.md) plus the testing folder.

## How a single work item should be executed

```text
1. Find the playbook.
2. Read the data-model file it depends on.
3. Read the RBAC and audit rules.
4. Implement.
5. Test the happy path, empty path, forbidden path, and failure path.
6. Record anything that changed the plan in the decisions log.
```

## File naming

- Folder numbers are the reading and delivery order.
- File numbers are the order inside a folder.
- `README.md` in a folder is the map, not the full content.

## What “done” looks like for documentation updates

If you change product behaviour, update:

1. the relevant playbook
2. the data model if a field changed
3. the decisions log if a locked choice changed
4. the first production release file if scope changed
