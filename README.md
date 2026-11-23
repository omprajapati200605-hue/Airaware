# AirAware

A responsive air-quality information dashboard built with React, Vite, Recharts, Leaflet, and the Open-Meteo Air Quality API.

## Run locally

```bash
npm install
npm run dev
```

Open the local URL printed by Vite.

## Production build

```bash
npm run build
npm run preview
```

The production files are generated in `dist/`.

## Deployment

This is a static Vite frontend and can be deployed to Render Static Sites, Vercel, Netlify, or another static host.

- Build command: `npm install && npm run build`
- Publish directory: `dist`
- No API key is required for the public Open-Meteo endpoints used by this demo.
- Configure SPA fallback/rewrite to `/index.html` if you later add client-side routing.

## Data and methodology notes

- Location search: Open-Meteo Geocoding API.
- Hourly pollutant concentrations: Open-Meteo Air Quality API.
- Map tiles: OpenStreetMap.
- AQI shown in the dashboard is an **estimate** calculated from available hourly pollutant concentrations using CPCB-style breakpoint interpolation and pollutant averaging windows (24-hour for particulate matter and selected gases; 8-hour for ozone and carbon monoxide) when sufficient hourly history is available. It is not an official CPCB-issued station AQI. This prototype should be validated against authoritative CPCB data and the full applicable technical specification before public-health use.
- Missing readings are not replaced with invented values.
- The map displays the selected coordinate and modeled grid context, not a fabricated network of monitoring stations.

## Before public launch

1. Verify data coverage and compare calculations against official CPCB references.
2. Replace legal-page contact placeholders with verified project-owner details.
3. Review privacy disclosures and third-party API/map licensing.
4. Add a custom domain and verify HTTPS.
5. Run `npm run build` and test on target devices and browsers.
6. Add server-side persistence only if user accounts, synced saved locations, or durable alert subscriptions are required.

## Features

- Location search and optional browser geolocation.
- Current pollutant concentrations and estimated Indian AQI category.
- 24-hour, 7-day, and 30-day chart filters.
- Interactive OpenStreetMap view centered on the selected location.
- Saved locations in browser local storage.
- CSV export of visible historical data.
- Browser notification permission flow for threshold checking while the page is open.
- Guidance, About, Privacy Policy, and Terms and Conditions pages.
