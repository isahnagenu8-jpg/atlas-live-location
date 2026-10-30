# Atlas — Live Location

A responsive browser-based GPS dashboard with a live OpenStreetMap, coordinate readout, accuracy radius, sharing/copying, JSON export, map-style toggle, theme switch, and a short local journey recorder.

## Files
- `index.html` — page structure
- `style.css` — responsive interface
- `app.js` — map and browser GPS behaviour

## Run locally
1. Open this folder in Visual Studio Code.
2. Start a local web server. For example, in the VS Code terminal run:
   ```bash
   py -m http.server 8000
   ```
3. Open `http://localhost:8000` in your browser.
4. Press **Find my location** and allow location access.

GPS usually requires a secure context: `localhost` works for local development, and a deployed website should use HTTPS. Opening `index.html` directly as a `file://` URL may prevent geolocation from working.

## Publish it online later
This is a static website, so it does not need a Python server or database. You can:
1. Create a GitHub repository and upload these four files (keep `index.html` at the repository root).
2. Enable GitHub Pages in the repository settings, or deploy the folder with Netlify or Vercel.
3. Buy a domain from a domain registrar.
4. Add the custom domain in your hosting provider's settings and copy the DNS records they give you into your registrar's DNS settings.
5. Wait for DNS/HTTPS setup to finish, then test GPS on your phone and computer.

Hosting provider screens and DNS records can change, so follow the exact instructions shown by the provider you choose.

## Important notes
- The page requests browser permission before reading location. The visitor can deny or revoke permission.
- Coordinates and journey points are kept in the page's memory and are not uploaded to an Atlas server. Refreshing or closing the page clears the in-progress journey.
- Location accuracy depends on the device, GPS reception, browser and network. Do not use this as an emergency location service.
- The map uses OpenStreetMap tiles and OpenTopoMap terrain tiles. Keep attribution visible and review each tile provider's usage policy before a high-traffic public launch; public tile services are not an unlimited free map-hosting service.
- Leaflet and map tiles load from third-party services, so an internet connection is required for the map.
