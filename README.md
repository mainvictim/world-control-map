# World control & sentiment map

A **borderless** world map that shows:

- **Military control / presence** — Who has bases, troops, or de facto control (e.g. US in Iraq, Russia in Syria). No traditional colonial or treaty-drawn borders.
- **Civilian resistance** — Where populations show high unhappiness or resistance to current controllers.

## How to view

Open `index.html` in a modern browser (Chrome, Firefox, Edge). No server required.  
If the land layer fails to load (CORS), the map falls back to a dark tile layer; the control and sentiment layers still work.

## Layers

- **Military control** — Colored zones by controlling power (US, Russia, China, Turkey, contested). Click zones for details.
- **Civilian resistance** — Yellow halos: high (strong), medium, or localized resistance. Toggle each layer with the buttons top-right.

## Data

Sample data is included for:

- Iraq (US presence), Syria (Russian + Turkish), Palestine/Israel (contested)
- Sahel/Libya (Russian/Wagner), Djibouti (US + Chinese), Eastern Europe (NATO)
- Pakistan/BRI (Chinese), Afghanistan (US residual)

To add or edit zones, edit the `militaryData` and `sentimentData` objects in `index.html`:

- **Military**: `geometry` = GeoJSON Point `[longitude, latitude]`, `properties.radius` = meters (influence zone), `properties.power` = `'US'|'Russia'|'China'|'Turkey'|'Other'`.
- **Sentiment**: `geometry` = Point, `properties.level` = `'high'|'medium'|'local'`.

You can replace or extend these with your own GeoJSON or API data.

## Tech

- Leaflet.js
- Natural Earth 110m land (no political borders) as base land layer
