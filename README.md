# LifeGit

LifeGit is a minimalist, GitHub‑inspired personal activity tracker.  Instead of focusing on rigid streaks or gamified badges, it presents your daily logs on a contribution‑style heatmap and computes a momentum score that decays gracefully when you take breaks.  The goal is to reinforce identity continuity rather than shame for missed days.

## Features

- **Multi‑commit logging:** LifeGit treats each day like a commit group.  You can add multiple commit messages in one session; each commit gets its own seven‑character hash and extracted hashtags (e.g. `#fitness`).
- **GitHub‑style heatmap:** A contribution calendar shows commit density over the past year.  Darker cells correspond to more commits on that day.
- **Universal search bar:** A single search input lets you filter by `#tags`, plain keywords or partial hashes.  Typing a few characters of a hash suggests matching commits.  Only commits satisfying all tokens are shown on the heatmap and in the lists.
- **Commit detail modal:** Clicking a commit in the daily list opens a modal with its full hash, timestamp, message and tags.  A handy button copies the hash to your clipboard.
- **Momentum engine:** A smooth exponential decay rewards recent activity without punishing breaks.  Momentum pauses rather than resets when you take time off, and friendly messages gently nudge you back into logging.
- **Local‑first:** All data lives in your browser using `localStorage`.  No sign‑up or backend is required.  Import/export functions let you back up your logs as JSON.

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
