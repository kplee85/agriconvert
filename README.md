# AgriConvert Pro

> Field-ready agricultural unit converter & calculator — built for Malaysian durian farming.
> Works fully offline as a PWA (Progressive Web App).

**Live URL:** https://kplee85.github.io/agriconvert/

---

## Changelog

### v1.3.2 — Elevation & Slope Tools
- **New: 📊 Elevation tab** inside GPS — 5th sub-tab alongside Stamp/Trees/Boundary/Distance
- All 4 elevation tools gated under the same RM 9.90 one-time premium unlock
- **📍 Elevation Stamp** — read altitude at current location, label and save up to 30 points, auto-calculates total terrain relief across saved stamps
- **📐 Slope A→B** — set two GPS points, auto-calculates gradient %, ratio 1:X, degrees °, water flow direction, and measurement error estimate
- **🗺️ Terrain Survey** — log up to 10 points across a plot, analyse to get highest/lowest point, total relief, average elevation, std deviation, overall gradient, terrain rating (Near Flat / Gentle / Moderate / Steep / Very Steep), and water flow direction
- **🎯 Target Deviation** — set a design target slope %, measure actual, shows deviation, status (✅ On target / 🔴 Too steep / 🔵 Too flat), actual vs ideal height difference
- Accuracy warning system: ✅ Good ≤3m · ⚠️ Fair ≤8m · ❌ Poor >8m with retry advice
- Uses GPS altitude (OS barometric sensor fusion) via `coords.altitude`
- All results copyable to clipboard, survey points exportable as CSV

### v1.3.1b — Token Validator Hotfix
- Relaxed token format regex to accept 3–8 chars in segment 3 (was strict 6)
- Fixes "Invalid token format" error on valid tokens generated from Google Sheets
- Updated error message to be format-agnostic

### v1.3.1 — Premium GPS System
- GPS tools require unlock after 14-day free trial
- One-time payment: RM 9.90 · Lifetime access · No renewals
- Soft-lock UI — tools visible but dimmed, tap any tool to see upgrade screen
- Upgrade modal with DuitNow / bank transfer payment details (placeholders to fill)
- Token system: format `AGRI-YYYY-XXXXX-XX` entered in app to activate
- WhatsApp + Google Form contact options after payment
- Settings → Premium shows live status: trial days left / active / locked
- 14-day free trial starts automatically on first app open

### v1.3.0 — GPS Tab
- New 4th main tab: GPS
- 📌 Location Stamp — GPS coordinates + note, save up to 50, copy or open in Google Maps
- 🌳 Tree Logger — log GPS per tree, auto-numbered T-001/T-002, custom label, CSV export
- 📐 Boundary Mapper — walk corners, Shoelace Formula → area in Acres/ha/Relong/m² + perimeter
- 📏 Distance Measurer — Point A to B, Haversine Formula → m/ft/chains + compass bearing
- OpenStreetMap via Leaflet.js when online (no API key)
- All GPS data persists offline in localStorage

### v1.2.0 — Pressure Feature
- New: Pressure converter — 5th tab in Convert (Bar · kPa · MPa · PSI · kg/cm² · atm · mmHg)
- New: Pressure Calculator — 4th panel in Calculate:
  - Nozzle Checker — pressure vs rated range → Safe / Too Low / Too High + droplet size
  - Flow Rate Estimator — rated flow at rated pressure → actual flow via Q ∝ √P + tank fill time
  - Gauge Reader — any unit → all 7 equivalents + sprayer quick-reference guide

### v1.1.0 — UI Polish
- Responsive CSS grid for result cards (1 col phone → 2 col tablet → 3 col PC)
- Fixed Spray Mix dose rate layout — no overflow or shift on small screens
- Service worker cache bumped to force update on all installed devices

### v1.0.0 — Initial Release
- 4 converter tabs: Area, Length, Weight, Volume (36 units total)
- 3 calculator modules: Spray Mix, Fertilizer Rate, Dilution %
- First-launch onboarding — choose unit system
- Conversion history (last 20, stored locally)
- Full PWA offline support via service worker
- Malaysian defaults: Acre · kg · L

---

## Features

### 📐 Converters (Free)
| Tab      | Units |
|----------|-------|
| Area     | m², Hectare, Acre, Rood, Square Pole, ft², 坪, 市亩, Relong |
| Length   | mm, cm, m, km, Inch, Foot, Yard, Chain, Rod, Link |
| Weight   | g, kg, Tonne, oz, lb, Bag 25kg, Bag 50kg, Pikul |
| Volume   | ml, cc, L, m³, fl oz, Pint, Quart, Gallon US, Gallon UK |
| Pressure | Bar, kPa, MPa, PSI, kg/cm², atm, mmHg |

### 🧪 Calculators (Free)
| Calculator  | What it does |
|-------------|--------------|
| Spray Mix   | Dose rate × tank size → product per tank + total for job |
| Fertilizer  | kg/ha or kg/tree → total kg + bags needed + RM cost estimate |
| Dilution %  | Target % or label rate → product + water volumes |
| Pressure    | Nozzle check · Flow rate estimator · Gauge unit reader |

### 📍 GPS Tools (Premium — RM 9.90 one-time)
| Tool            | What it does |
|-----------------|--------------|
| Location Stamp  | One-tap GPS coordinate + note → save / copy / open in Maps |
| Tree Logger     | Log GPS per tree, auto-numbered T-001+, CSV export to Notion |
| Boundary Mapper | Walk corners → auto area in Acres / ha / Relong + perimeter |
| Distance        | Point A to B → m / ft / chains + compass bearing |

### 📊 Elevation Tools (Premium — same RM 9.90 unlock)
| Tool             | What it does |
|------------------|--------------|
| Elevation Stamp  | Read altitude at location → label, save, compare relief |
| Slope A→B        | Two-point gradient → % · ratio · degrees + water flow direction |
| Terrain Survey   | Up to 10 points → terrain profile + drainage risk rating |
| Target Deviation | Compare actual slope vs design target → deviation + ideal height diff |

### ⚙️ Settings
- Unit system (Malaysian / Metric / Imperial / Mixed)
- Premium GPS status + token entry
- Conversion history (last 20, clearable)

---

## Premium GPS + Elevation — How to Unlock

1. Open the GPS tab — free 14-day trial starts automatically
2. After trial, tap any GPS or Elevation tool → upgrade screen appears
3. Pay **RM 9.90** via DuitNow / bank transfer (details shown in app)
4. Send your email + payment screenshot via WhatsApp or Google Form
5. Receive token: `AGRI-2026-XXXXX-XX`
6. Go to Settings → Premium → Enter Token → Activate
7. All GPS and Elevation tools unlocked permanently — no renewals ever

**Contact:** kplee85@gmail.com

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

1. Repo → **Settings** → **Pages** → Branch: `main` / root → **Save**
2. Live at: `https://kplee85.github.io/agriconvert/`

**Install on Android:** Open URL in Chrome → ⋮ → **Add to Home Screen**

**Share:** Send URL via WhatsApp — opens and installs instantly on any phone.

---

## Updating

1. Edit `index.html` and/or `sw.js` on GitHub (click file → ✏️ edit)
2. **Always bump `CACHE_NAME`** in `sw.js` — e.g. `agriconvert-v1.3.3`
3. Commit — GitHub Pages updates in ~1 minute
4. Hard refresh on phone: hold reload → **Hard Reload**

---

## Roadmap

### v1.3.x — Fixes & Polish
- [ ] Icon design update (Scale with Leaf concept — on hold)
- [ ] Bug fixes based on field feedback

### v1.4 — More Converters
- [ ] Temperature — °C · °F · Kelvin (soil temp, cold storage, heat stress)
- [ ] Yield Normalizer — kg/tree · tonne/acre · MT/ha (harvest benchmarking)

### v1.5 — Smarter Calculators
- [ ] NPK Nutrient Calculator — break down fertilizer label (15-15-15) into pure N/P/K per bag and per acre
- [ ] Saved Spray Tank Presets — name and recall tank sizes (Knapsack 16L, Power Sprayer 200L)

### v1.6 — Field Productivity
- [ ] Currency Converter — RM · USD · SGD for input cost and export pricing
- [ ] WhatsApp Share — send calculator results as formatted message to workers or suppliers

### v2.0 — Farm OS Integration
- [ ] Notion sync — push spray records, fertilizer applications, and yield data into Farm OS
- [ ] Conversion history export — send session log to Telegram or save to Notion daily log
- [ ] Orchard profile — store orchard size, tree count, soil type; auto-fill calculator fields
