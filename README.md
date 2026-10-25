# Kuyastop

Kuyastop is a phone-first React commute-alert prototype built with Vite. It follows the supplied wireframes and supports English and Filipino.

## Run locally

1. Open this folder in VS Code.
2. In the integrated terminal, run npm install.
3. Run npm run dev and open the local URL printed by Vite.

## Commute features

- Choose an MRT/LRT route, or a motorcycle, jeepney, bus, or car journey.
- Train journeys advance by station. Road journeys move along the route and alert by proximity.
- Add several people and choose Every commute, Missed stop only, or Never for each.
- A Share trip action appears for people marked Every commute. Missed-stop recovery also offers updates to selected recipients.
- SMS opens as a draft for the rider to review and send. No contact message is sent automatically.
- Select a starting point or allow device location. The route marker follows browser GPS when available; the sample journey marker moves during the local preview.
- Voice, vibration, notifications, location and audio depend on browser/device permissions and support. The screen is not held awake.

## Netlify

Build command: npm run build
Publish directory: dist

Google Maps directions open in Google Maps using the selected origin, destination and travel mode. For automated contact messages or a live backend, add an SMS/push service and server-side consent handling before launch.
## Interactive maps

The route setup and active commute screens include an interactive Leaflet map with OpenStreetMap street tiles, zoom controls, stop markers, a route line, and a moving location pin. Choose **Use device location** and allow location access to follow the phone while the commute screen is open. In preview mode, the pin moves along the selected route. A network connection is needed to load map tiles. OpenStreetMap's standard tiles are free to view but best-effort, with no uptime guarantee; keep visible attribution and follow the tile usage policy. For a high-traffic public launch, choose a hosted OSM tile provider with a plan that fits your use or host tiles yourself.
## Searchable, map-picked routes and bus stops

- Enter a place name and press Search to get up to five Philippines place results, or select From/To and tap the map to place a pin. Search is explicit rather than autocomplete to respect the public geocoder's rate limits.
- Road journeys request a street route from the public OSRM demo router. If routing is unavailable, the map shows the selected waypoints as a fallback. Train routes follow the selected sample stations.
- Bus mode includes one EDSA Carousel sample route from Ayala to Guadalupe with an intermediate Buendia stop. The rider can toggle the alert for each intermediate stop. In preview, the bus advances stop-by-stop; with device GPS enabled, the app announces a stop after the phone remains within roughly 120 m for four seconds. This detects the rider phone near the sample stop; it is not a live bus fleet feed.
- Road alerts play a repeating tone that becomes louder and more frequent near the destination.

The public Photon geocoder and OSRM demo router are free to try and need no API key, but are best-effort services with usage limits and no service guarantee. For launch, use an approved hosted service or self-host routing/geocoding if demand grows. See the [Photon usage guidance](https://github.com/komoot/photon) and [OSRM demo server policy](https://github.com/Project-OSRM/osrm-backend/wiki/Api-usage-policy).
