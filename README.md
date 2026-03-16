# AgriConvert Pro

> Field-ready agricultural unit converter & calculator — built for Malaysian durian farming.
> Works fully offline as a PWA (Progressive Web App).

**Live URL:** https://kplee85.github.io/agriconvert/

---

## Changelog

### v1.3.1 — Premium GPS System
- **GPS tools now require unlock after 14-day free trial**
- One-time payment: RM 9.90 · Lifetime access · No subscription
- Soft-lock UI — tools visible but dimmed, tap any tool to see upgrade screen
- Upgrade modal with DuitNow / bank transfer payment details
- Token activation system — enter AGRI-XXXX-XXXXXX-XX token to unlock
- WhatsApp + Google Form contact options after payment
- Settings → Premium shows live status (trial / active / locked)
- 14-day free trial starts automatically on first app open — no action needed

### v1.3.0 — GPS Tab (4 tools)
- **New main tab: GPS** — sits between Calculate and Settings
- 📌 **Location Stamp** — one-tap GPS coordinate capture with note, save up to 50, copy or open in Google Maps
- 🌳 **Tree Logger** — log GPS position per tree, auto-numbered T-001/T-002..., custom label override, CSV export for Notion/Farm OS
- 📐 **Boundary Mapper** — walk plot perimeter, tap at each corner, Shoelace Formula calculates area in Acres/ha/Relong/m² + perimeter
- 📏 **Distance Measurer** — set Point A and B, Haversine Formula gives distance in m/ft/chains + compass bearing
- OpenStreetMap via Leaflet.js shows live map when online (no API key needed)
- All GPS data persists offline in localStorage

### v1.2.0 — Pressure Feature
- **New: Pressure converter** — 5th tab in Convert (Bar · kPa · MPa · PSI · kg/cm² · atm · mmHg)
- **New: Pressure Calculator** — 4th panel in Calculate with 3 modes:
  - Nozzle Checker — operating pressure vs nozzle rated range → Safe / Too Low / Too High + droplet size
  - Flow Rate Estimator — rated flow at rated pressure → estimated flow at actual pressure (Q ∝ √P) + tank fill time
  - Gauge Reader — any pressure unit → all 7 equivalents + sprayer quick-reference guide

### v1.1.0 — UI Polish
- Responsive CSS grid for result cards (1 col phone → 2 col tablet → 3 col PC)
- Fixed Spray Mix dose rate row — stable two-segment layout, no overflow on mobile
- Service worker cache bumped to force update on all devices

### v1.0.0 — Initial Release
- 4 converter tabs: Area, Length, Weight, Volume (36 units total)
- 3 calculator modules: Spray Mix, Fertilizer Rate, Dilution %
- First-launch onboarding — choose unit system (Malaysian / Metric / Imperial / Mixed)
- Conversion history (last 20, stored locally, clearable)
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
| Location Stamp  | Tap → GPS coordinates + note → save / copy / open in Maps |
| Tree Logger     | Log GPS per tree, auto-numbered, CSV export to Notion |
| Boundary Mapper | Walk corners → auto area (Acres / ha / Relong) + perimeter |
| Distance        | Point A to B → distance in m/ft/chains + compass bearing |

### ⚙️ Settings
- Unit system preference (Malaysian / Metric / Imperial / Mixed)
- Premium GPS status + token entry
- Conversion history (last 20, clearable)

---

## Premium GPS — How to Unlock

1. Open the GPS tab in the app — free 14-day trial starts automatically
2. After trial, tap any GPS tool → upgrade screen appears
3. Pay **RM 9.90** via DuitNow / bank transfer (details shown in app)
4. Send your email + payment screenshot via WhatsApp or Google Form
5. Receive your token: `AGRI-2026-XXXXXX-XX`
6. Go to Settings → Premium → Enter Token → Activate
7. GPS tools unlocked permanently — lifetime access, no renewals

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

1. Go to repo → **Settings** → **Pages**
2. Source: Deploy from branch → `main` / `root`
3. Click **Save**
4. Live at: `https://kplee85.github.io/agriconvert/`

**Install on Android:**
1. Open URL in Chrome → tap ⋮ → **Add to Home Screen**
2. Opens full screen, works fully offline

**Share with workers:** Send URL via WhatsApp — opens and installs instantly.

---

## Updating the App

1. Edit `index.html` and/or `sw.js` on GitHub (click file → ✏️ edit)
2. Always bump `CACHE_NAME` in `sw.js` — e.g. `agriconvert-v1.3.2`
3. Commit — GitHub Pages updates in ~1 minute
4. Hard refresh on phone: hold reload → **Hard Reload**

---

## Roadmap

### v1.3.x — Fixes & Polish
- [ ] Bug fixes and UI refinements based on field feedback
- [ ] Icon design update (Scale with Leaf concept)

### v1.4 — More Converters
- [ ] **Temperature** — °C · °F · Kelvin (soil temp, cold storage, heat stress)
- [ ] **Yield Normalizer** — kg/tree · tonne/acre · MT/ha (harvest benchmarking)

### v1.5 — Smarter Calculators
- [ ] **NPK Nutrient Calculator** — break down fertilizer label (e.g. 15-15-15) into pure N/P/K per bag and per acre
- [ ] **Saved Spray Tank Presets** — name and save tank sizes (Knapsack 16L, Power Sprayer 200L)

### v1.6 — Field Productivity
- [ ] **Currency Converter** — RM · USD · SGD for input cost and export pricing
- [ ] **WhatsApp Share** — send calculator results as formatted message to workers or suppliers

### v2.0 — Farm OS Integration
- [ ] **Notion sync** — push spray records, fertilizer applications, and yield data into Farm OS
- [ ] **Conversion history export** — send session log to Telegram or save to Notion daily log
- [ ] **Orchard profile** — store orchard size, tree count, soil type; auto-fill calculator fields
