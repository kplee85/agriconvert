# AgriConvert Pro

> Field-ready agricultural unit converter & calculator — built for Malaysian durian farming.
> Works fully offline as a PWA (Progressive Web App).

**Live URL:** https://kplee85.github.io/agriconvert/

---

## Changelog

### v1.1.0 — UI Polish
- **Even result cards** — responsive CSS grid (1 col phone → 2 col tablet → 3 col PC)
- **Fixed Spray Mix layout** — dose rate row uses stable two-segment grid, no overflow shift
- **Responsive design** — scales cleanly from 360px phones to full PC browser windows
- **Tighter card layout** — badges and copy icon grouped right column, no misalignment
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

### Converters
| Tab    | Units |
|--------|-------|
| Area   | m², Hectare, Acre, Rood, Square Pole, ft², 坪, 市亩, Relong |
| Length | mm, cm, m, km, Inch, Foot, Yard, Chain, Rod, Link |
| Weight | g, kg, Tonne, oz, lb, Bag 25kg, Bag 50kg, Pikul |
| Volume | ml, cc, L, m³, fl oz, Pint, Quart, Gallon US, Gallon UK |

### Calculators
| Calculator  | What it does |
|-------------|--------------|
| Spray Mix   | Dose rate × tank size → product per tank + total for job |
| Fertilizer  | kg/ha or kg/tree → total kg + bags needed + cost estimate |
| Dilution %  | Target % or label rate → product + water volumes |

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

## Deploy

### GitHub Pages
Settings → Pages → Source: Deploy from branch → main / root
Live at: https://kplee85.github.io/agriconvert/

### Local NAS
Copy folder to NAS web root → http://192.168.0.111/agriconvert/

### Install on Android
Open URL in Chrome → ⋮ → Add to Home Screen

---

## Updating

1. Edit files on GitHub
2. Bump `CACHE_NAME` in `sw.js` (e.g. `agriconvert-v1.2.0`)
3. Commit — GitHub Pages updates in ~1 minute

---

## Roadmap

- [ ] v1.2 — Tree Density & Spacing calculator
- [ ] v1.2 — Yield normalizer (kg/tree, tonne/acre)
- [ ] v1.3 — Saved spray tank presets
- [ ] v1.3 — WhatsApp share on calculator results
- [ ] v2.0 — Farm OS Notion integration
