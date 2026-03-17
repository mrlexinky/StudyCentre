# Revision Command Centre

A single-page revision management app for UK A-level students, covering Mathematics, Further Maths, Physics, and Computer Science.

## Features

- **Home** — Today's date, next exam countdown, daily itinerary prompt generator for Claude, session feedback prompt
- **Traffic Lights** — Rate every specification topic as red/amber/green across all four subjects
- **Past Papers** — Log papers with scores and wrong-topic notes; tracks weekly targets and recommends next paper
- **Exam Countdown** — All 12 exams sorted by date with colour-coded day counters and an overall readiness bar

## Deployment

### GitHub Pages

1. Fork this repository
2. Go to **Settings → Pages**
3. Under **Source**, select **Deploy from a branch**
4. Choose **main** branch and **/ (root)** folder
5. Click **Save**
6. Your site will be live at `https://<username>.github.io/<repo-name>/`

### Local

Open `index.html` directly in any browser. No build step, no dependencies.

## Data Storage

All data lives in the browser's `localStorage` under the key `rcc_v1`. Data is **not** synced between devices or browsers.

### Transferring data between devices

1. On the source device, open the browser console (`F12` → Console) and run:
   ```js
   copy(localStorage.getItem('rcc_v1'))
   ```
   This copies the JSON data to your clipboard.

2. On the target device, open the browser console and run:
   ```js
   localStorage.setItem('rcc_v1', '<paste your JSON here>')
   ```
   Then refresh the page.

## Tech

- Single `index.html` file — all CSS and JS inlined
- No frameworks, no build tools, no external dependencies
- Hash-based routing (`#home`, `#traffic`, `#papers`, `#countdown`)
- Respects `prefers-color-scheme` for automatic dark mode
