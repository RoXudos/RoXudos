# Interactive map

## Steps

1. Add MapLibre to the Live mini-map and the full `/map` page.
2. Load authorised GeoJSON for the event.
3. Draw site boundary, zones, locations.
4. Edit mode (`map.update`): add point, draw polygon, move, delete with confirm.
5. Click location → drawer: name, type, open incidents, open tasks.
6. Live pins for active incidents (no safeguarding).
7. Filter chips for location types including accessibility.
8. List fallback on the same page.

## Basemap

Start with a working OSM style that does not require a card. Add a paid tile provider only if the default is unreadable in a dark room.

## Done when

A control manager can place Main Stage, Gate 2, and a medical point, then see a medical incident pin appear on that point after create (realtime or refresh).
