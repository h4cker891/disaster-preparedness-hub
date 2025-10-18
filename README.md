# Disaster Preparedness Hub

Lightweight single-file web app that provides localized emergency alerts, evacuation resources, and preparedness tools.

## What this is

- A responsive HTML/CSS/JS single-page app built for quick local deployments.
- Uses OpenStreetMap/Leaflet for map display and NOAA (`api.weather.gov`) for alerts where available.
- Includes mobile-friendly layout, a ZIP code onboarding overlay, and visual styling with a glassy UI and animated background.

## Files

- `index.html` — the entire app (styles, markup, and scripts) contained in a single file for simplicity.
- `logo.png` — site logo used in the header and as the favicon (place in the project root).

## Dependencies

- External CDNs used:
  - Tailwind CSS (for font stack and utility defaults)
  - Leaflet (mapping)
  - tsParticles (background particle effects)

No build step required — open `index.html` in a modern browser.

## How to use

1. Place `logo.png` in the same directory as `index.html`.
2. Open `index.html` in your browser.
3. On first load, the app will ask for your ZIP code to load localized alerts and nearby shelter info.

## Structure & Key Areas

- Header: brand + ZIP input and lookup controls.
- ZIP overlay: modal-style onboarding that sets the main ZIP and triggers a lookup.
- Main grid: map, active alert list, quick actions, shelter info, and a small quiz.
- Visuals: glassmorphic cards, morphing blob background, interactive particles.

## Customization

- Styles: edit the `<style>` block at the top of `index.html`.
- Particle settings: adjust the `tsParticles` config in the `window.tsParticles.load` call.
- Alerts: `fetchWeatherAlerts` queries `api.weather.gov` and returns simplified alert objects.

## Troubleshooting

- If the map doesn't render, ensure the device has network access and the Leaflet tile URL is reachable.
- If ZIP lookups fail, the app uses Nominatim; rate limits or CORS restrictions could affect lookups.
- If the "Continue" button on the ZIP overlay doesn't respond: ensure `index.html` is opened via `file://` or served from a local server; some browsers restrict script behavior when opened directly from the filesystem.

## Acknowledgements

- Styling help for the glassmorphism, blob background, and general visual polish was provided by ChatGPT (styling assistance only).

