# LifeGit

LifeGit is a minimalist, GitHub‑inspired personal activity tracker.  Instead of focusing on rigid streaks or gamified badges, it presents your daily logs on a contribution‑style heatmap and computes a momentum score that decays gracefully when you take breaks.  The goal is to reinforce identity continuity rather than shame for missed days.

## Features

- **Freeform logging:** Write anything about your day.  Hashtags (e.g. `#fitness`) are automatically extracted so you can organise later.
- **Heatmap calendar:** A GitHub‑style calendar visualises how many times you logged on each day over the past year.  More logs means a darker cell.
- **Tag filtering:** Filter your timeline by entering one or more hashtags.  Only entries containing all specified tags will be counted and displayed.
- **Momentum engine:** A simple algorithm computes a momentum score based on how recently you’ve logged.  It decays smoothly instead of resetting to zero when you skip days.  Friendly messages gently welcome you back.
- **Local‑first:** Everything is stored in your browser using `localStorage` or `IndexedDB`.  There’s no signup or backend.  You can export or import your data as JSON if you need to back it up.

## Getting started

1. Install the dependencies using your favourite package manager:

   ```sh
   npm install
   ```

2. Start the development server:

   ```sh
   npm run dev
   ```

3. Open <http://localhost:5173> in your browser.  You should see the LifeGit interface with an input area, a heatmap, filters and stats.

4. Build for production when you’re ready:

   ```sh
   npm run build
   ```

   The compiled assets will be output to the `dist/` directory.  You can run `npm run preview` to test the production build locally.

## Project structure

- `src/` – contains all application code
  - `main.jsx` – entry point that mounts the React app
  - `App.jsx` – top‑level component orchestrating state, routes and layout
  - `components/` – reusable UI pieces like the entry form, heatmap, tag filter, stats display and per‑day entry list
  - `utils/` – helper modules for interacting with `localStorage` and computing momentum/streak scores
  - `index.css` – Tailwind and custom styles
- `index.html` – the single page into which the React app is injected
- `tailwind.config.js` – Tailwind configuration with custom colours for heatmap squares
- `vite.config.js` – Vite configuration enabling React and local dev server
- `postcss.config.js` – PostCSS configuration used by Tailwind
- `package.json` – dependency declarations and npm scripts

## Future ideas

This project is deliberately small so you can extend it freely.  Some possibilities include:

- Persist data in a backend service and enable user accounts.
- Integrate with external APIs (e.g. GitHub, Google Calendar) to automatically generate logs.
- Suggest tags using basic NLP or user history.
- Add weekly or monthly summaries and charts.
- Introduce gamified elements (badges, achievements, etc.) in a gentle way.

## License

MIT
