# Maps architecture

FPR includes an interactive site map.

## Renderer

MapLibre GL in the control-room web app.

## Basemap

Start with a calm, low-contrast raster or vector basemap (OSM-derived or a commercial tile with a DPA). The site overlay must read first. The basemap is context, not the product.

## Site overlay

Store on the event:

| Object | Geometry | Properties |
| --- | --- | --- |
| Site boundary | Polygon | name |
| Zone | Polygon | name, access level, colour |
| Location | Point (or small polygon) | type, name, status |
| Route (optional) | LineString | parade / course / evacuation |
| Closure (optional) | LineString or Polygon | road closure |

Use GeoJSON in Postgres (`jsonb` is fine for FPR; `postgis` is better if you already enable it — **enable PostGIS** on Supabase from the start so you do not migrate later).

## Location types

Seed:

- stage, entrance, exit, emergency_exit
- toilet, accessible_toilet, bar, food, vendor
- medical, welfare, safeguarding_point
- security_post, control_room
- fire_point, cctv, generator, infrastructure
- car_park, accessible_parking
- quiet_area, viewing_platform
- assembly, parade_start, parade_finish

## Interaction

- Click location → drawer with open incidents, tasks, and status
- Filter by type
- Toggle zones
- Edit mode only with `map.update`
- Snap-enough editing for a tablet in a production office; precision GIS can wait

## Live layer

Show counts or pins for **active incidents** and **open urgent tasks**.

Do not show safeguarding case pins on the shared map.

Medical incidents may show as “Medical — Main Stage — High” without treatment notes.

## Performance

A festival map is hundreds of features, not millions. Load the event’s GeoJSON in one authorised request and cache it in memory. Refresh on map-update realtime events.

## Accessibility

Map is not the only way to find a location. Every location exists in a searchable list. Keyboard users can pick from the list.
