---

<h1 align="center">⛅ SkyLumin - WeatherApp</h1>

<div align="center">Live, interactive weather UI built with React + Vite 

[![Vite](https://img.shields.io/badge/Vite-DevServer-brightgreen)](https://vitejs.dev/)
[![React](https://img.shields.io/badge/React-17%2B-blue)](https://reactjs.org/)

SkyLumin is a small weather application that queries OpenWeatherMap to show current conditions with animated backgrounds and helpful weather metrics.</div>

---

## Quick Links
- **Source:** `src/` (entry: `src/main.jsx`, UI: `src/App.jsx`)
- **Components:** `src/components/Helper.jsx`, `src/components/Icons.jsx`, `src/components/WeatherBackground.jsx`

---

## Interactive Highlights
- Search for a city by typing 3+ characters — suggestions appear automatically.
- Click a suggestion to load that location's weather (uses lat/lon geocoding).
- Toggle temperature units with the °C/°F button after a search.
- Use the "New Search" button to return to the search view.
- Animated backgrounds change based on the reported weather condition and day/night.

**Security note:** This project currently includes an OpenWeatherMap API key in `src/App.jsx`. For production, move the key to environment variables and do not commit it.

---

## Try it locally
1. Install dependencies:

```bash
npm install
```

2. Start the dev server:

```bash
npm run dev
```

3. Open the app in your browser (Vite usually serves at `http://localhost:5173`).

4. Build for production:

```bash
npm run build
npm run preview
```

---

## What to try (interactive checklist)
- Type a city name (e.g., "Lon") and pick a suggestion.
- Click the temperature unit button to switch between Celsius and Fahrenheit.
- Inspect the animated background — it changes for `Clear`, `Rain`, `Snow`, `Thunderstorm`, etc.

---

## Files of interest
- `src/App.jsx` — main UI, search form, API requests, unit toggle, and rendering logic.
- `src/components/Helper.jsx` — utility helpers: temperature conversion, wind direction, humidity label, visibility formatting.
- `src/components/Icons.jsx` — small icon components used for humidity, wind, visibility, sunrise/sunset.
- `src/components/WeatherBackground.jsx` — picks GIFs or a fallback video based on current weather condition and day/night.

---

## Implementation details
- Geocoding suggestions: OpenWeatherMap Geocoding API (`geo/1.0/direct`) with a 500ms debounce on user input.
- Weather: OpenWeatherMap current weather endpoint with `units=metric` by default.
- Temperature conversion: done client-side via `convertTemperature` in `Helper.jsx`.

---

## Development tips
- To remove the hard-coded API key, create a `.env` file and reference it as `import.meta.env.VITE_WEATHER_API_KEY` in `src/App.jsx`.
- The app uses Tailwind-like utility classes. If you change styles, check `index.css` and `App.css` for any animations or class utilities.

---

## Contributing
- Bug reports and small fixes: open an issue or a PR.
- Suggested improvements: caching search results, graceful API error/exhaustion handling, backend proxy for the API key.

---

