# Why this stack

## The constraints

- UK/GDPR-friendly default region
- Production-grade staging, backups, monitoring
- Multi-tenant isolation
- Realtime control room
- Interactive map
- File uploads
- Small or unknown implementation team
- Must not take a year of platform engineering before the first log line

## Why Next.js

- One language for UI and server
- Good enough auth session model with Supabase
- Easy desktop control-room app
- Same API surface can later serve a PWA
- Hiring and AI-agent familiarity is high

## Why Postgres + RLS

Event data is relational: events, people, incidents, timelines, permissions.

Row Level Security is the tenant-isolation backstop. If an application bug forgets `organisation_id` in a query, the database should still refuse other tenants’ rows.

## Why Supabase

For this product it is the shortest path to:

- hosted Postgres in London
- point-in-time recovery
- auth
- realtime
- storage (if you want a fallback; R2 is still preferred for files)
- local `supabase start` for developers

You can leave Supabase later. You cannot leave a wrong data model later.

## Why R2 instead of only Supabase Storage

- Cheaper egress
- S3-compatible
- EU jurisdiction bucket
- Clear separation: database in Supabase, blobs in object storage

Incident photos still need an authorisation check before a signed URL is issued.

## Why MapLibre

- No mandatory vendor lock for the renderer
- GeoJSON for zones and routes
- Can work later with offline tiles
- Good enough for a control-room site overlay

Mapbox is allowed only if you need their tiles and accept the DPA. The application code should talk MapLibre either way.

## Why not AWS first

AWS can do all of this. It is the right later home if a customer requires it. It is the wrong day-one home for a founder-plus-unknown-team product: VPC, IAM, ECS, and RDS will consume the first production release.

The exit hatch is documented in [03-alternatives-considered.md](03-alternatives-considered.md).
