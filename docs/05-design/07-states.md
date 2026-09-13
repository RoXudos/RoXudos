# Empty, loading, error, degraded

## Empty

Tell the user what to do.

- No incidents: “No active incidents. File one if something is happening.”
- No map: “Add a site boundary and a few locations. The live map is empty until you do.”
- No programme: “Add the next item. NOW/NEXT will stay blank until then.”

Do not show a cute illustration of a sad radio.

## Loading

Skeleton the mosaic tiles. Do not block the whole page if only weather is slow. Weather can fail independently.

## Error

- Say what failed
- Offer retry
- Keep the last good live data on screen if this is a refresh failure, with a time stamp

## Degraded

- Realtime down: banner + polling
- Weather API down: “Weather unavailable”
- Map tiles down: still show GeoJSON on an empty canvas if possible

## Offline (FPR)

If the browser is offline, say so. Disable the green “saved” state. Queue is Phase C.
