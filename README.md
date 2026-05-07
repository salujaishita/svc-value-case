# SVC Value Case Tool

Internal Accenture tool for generating sustainability value cases for client pitches.

---

## Setup (one time, ~10 minutes)

### Prerequisites
- Node.js installed → https://nodejs.org (download the LTS version, just click through the installer)
- That's it.

### Steps

```bash
# 1. Open a terminal / command prompt in this folder
cd svc-value-case

# 2. Install dependencies (only needed once)
npm install

# 3. Run locally
npm start
# Opens automatically at http://localhost:3000
```

### Build for deployment (hand to IT)

```bash
npm run build
```

This creates a `build/` folder. Hand the entire `build/` folder to IT and ask them to host it as a static web app on internal Azure or SharePoint.

---

## File structure

```
src/
  engine.js   ← All calculation logic (mirrors the Excel model)
  App.js      ← All screens and UI
  App.css     ← All styling
```

**To update a formula:** edit `src/engine.js` only — it's clearly commented.
**To add an initiative:** add it to the `INITIATIVES` object in `engine.js`.
**To change styling:** edit `App.css`.

---

## Screens

1. **Input screen** — client details, financials, objectives, initiative toggles
2. **Output screen** — headline value, KPI cards, 4 tab views:
   - Overview (value by lever chart + primary/secondary breakdown)
   - Sub-lever detail (full initiative table)
   - Value composition (waterfall)
   - NPV timeline (discounted cumulative chart)

---

## Deployment options (internal)

| Option | Effort | Notes |
|---|---|---|
| Azure Static Web Apps | Low | Ask IT for an internal static web app slot |
| SharePoint Framework (SPFx) | Medium | Requires SPFx packaging — IT can help |
| Internal IIS / web server | Low | Drop the `build/` folder into any web server |
