# Backups

## Database

Supabase Pro PITR on production. Know:

- How far back you can restore
- How to restore to a **new** project, not over a live event
- Who is allowed to press restore

## Files

R2 versioning on if available. If not, document the risk: deleted photos are gone.

## Drill

Once before first real event, and every quarter:

1. Restore yesterday’s DB to a throwaway project.
2. Sign in as a staging-like user.
3. Open one incident and one file.
4. Write the date of the drill in a company note.

If you have never restored, you do not have backups. You have hope.
