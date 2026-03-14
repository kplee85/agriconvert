# AgriConvert Pro

> Field-ready agricultural unit converter & calculator — built for Malaysian durian farming.
> Works fully offline as a PWA (Progressive Web App).

**Live URL:** https://kplee85.github.io/agriconvert/

---

## Changelog

### v1.2.0 — Pressure Feature
- **New: Pressure converter** — 5th tab in Convert (Bar · kPa · MPa · PSI · kg/cm² · atm · mmHg)
- **New: Pressure Calculator** — 4th panel in Calculate with 3 modes:
  - **Nozzle Checker** — operating pressure vs nozzle rated range → Safe / Too Low / Too High + droplet size estimate
  - **Flow Rate Estimator** — rated flow at rated pressure → estimated flow at actual pressure (Q ∝ √P) + tank fill time
  - **Gauge Reader** — any pressure unit → all 7 equivalents simultaneously + sprayer quick-reference guide

### v1.1.0 — UI Polish
- **Even result cards** — responsive CSS grid (1 col phone → 2 col tablet → 3 col PC)
- **Fixed Spray Mix layout** — dose rate row uses stable two-segment grid, no overflow shift on mobile
- **Responsive design** — scales cleanly from 360px phones to full PC browser windows
- **Service worker cache bumped** — forces update on next visit

### v1.0.0 — Initial Release
- 4 converter tabs: Area, Length, Weight, Volume (36 units total)
- 3 calculator modules: Spray Mix, Fertilizer Rate, Dilution %
- First-launch onboarding with unit system selection
- Conversion history (last 20, stored locally)
- Full PWA offline support via service worker
- Malaysian defaults: Acre · kg · L

---

## Features

### 📐 Converters
| Tab      | Units |
|----------|-------|
| Area     | m², Hectare, Acre, Rood, Square Pole, ft², 坪, 市亩, Relong |
| Length   | mm, cm, m, km, Inch, Foot, Yard, Chain, Rod, Link |
| Weight   | g, kg, Tonne, oz, lb, Bag 25kg, Bag 50kg, Pikul |
| Volume   | ml, cc, L, m³, fl oz, Pint, Quart, Gallon US, Gallon UK |
| Pressure | Bar, kPa, MPa, PSI, kg/cm², atm, mmHg |

### 🧪 Calculators
| Calculator    | What it does |
|---------------|--------------|
| Spray Mix     | Dose rate × tank size → product per tank + total for job |
| Fertilizer    | kg/ha or kg/tree → total kg + bags needed + cost estimate |
| Dilution %    | Target % or label rate → product + water volumes |
| Pressure      | Nozzle check · Flow rate estimator · Gauge unit reader |

### ⚙️ Settings
- Unit system preference (Malaysian / Metric / Imperial / Mixed)
- Conversion history (last 20, clearable)
- Offline-first via service worker

---

## File Structure

```
agriconvert-pwa/
├── index.html        ← Entire app (HTML + CSS + JS)
├── manifest.json     ← PWA metadata & icon config
├── sw.js             ← Service worker (offline caching)
├── icons/
│   ├── icon-192.png
│   └── icon-512.png
└── README.md
```

---

## Deploy — GitHub Pages

All files are served from the `main` branch root.

**Enable GitHub Pages:**
1. Go to repo → **Settings** → **Pages**
2. Source: Deploy from branch → `main` / `root`
3. Click **Save**
4. Live at: `https://kplee85.github.io/agriconvert/`

**Install on Android:**
1. Open the URL in Chrome
2. Tap ⋮ → **Add to Home Screen**
3. Opens full screen, works fully offline

**Share with workers:**
Send the URL via WhatsApp — anyone can open and install instantly.

---

## Updating the App

Whenever a new version is ready:
1. Edit `index.html` and `sw.js` on GitHub directly (click file → ✏️ edit)
2. **Always bump `CACHE_NAME`** in `sw.js` — e.g. `agriconvert-v1.3.0`
   - This forces all installed PWAs to update on next visit
3. Commit changes — GitHub Pages goes live within ~1 minute
4. Hard refresh on phone: hold reload → **Hard Reload**

---

## Roadmap

### v1.3 — More Converters
- [ ] **Temperature** — °C · °F · Kelvin (soil temp, cold storage, heat stress)
- [ ] **Yield Normalizer** — kg/tree · tonne/acre · MT/ha (harvest benchmarking per season)

### v1.4 — Smarter Calculators
- [ ] **NPK Nutrient Calculator** — break down fertilizer label (e.g. 15-15-15) into pure N, P₂O₅, K₂O per bag and per acre; compare products side by side
- [ ] **Saved Spray Tank Presets** — save named tanks (Knapsack 16L, Power Sprayer 200L) and recall instantly in Spray Mix calculator

### v1.5 — Field Productivity
- [ ] **Currency Converter** — RM · USD · SGD for input cost comparisons and export pricing
- [ ] **WhatsApp Share** — share calculator results directly as a formatted message to workers or suppliers

### v2.0 — Farm OS Integration
- [ ] **Notion sync** — push spray records, fertilizer applications, and yield data directly into Farm OS Notion database
- [ ] **Conversion history export** — send session log to Telegram or save to Notion daily log
- [ ] **Orchard profile** — store orchard size, tree count, soil type; auto-fill calculator fields from saved profile
