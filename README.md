# AgriConvert Pro v1.0.0
Agricultural unit converter & calculator — built for Malaysian durian farming.

## Files
```
agriconvert-pwa/
├── index.html      ← Main app (all code inside)
├── manifest.json   ← PWA config
├── sw.js           ← Service worker (offline support)
├── icons/
│   ├── icon-192.png
│   └── icon-512.png
└── README.md
```

## Deploy Options

### Option A — Your NAS (192.168.0.111)
1. Copy the entire folder to your NAS web root
2. Enable the HTTP server on your NAS
3. Access from any phone on farm WiFi: `http://192.168.0.111/agriconvert/`
4. On Android Chrome: tap ⋮ → "Add to Home Screen"

### Option B — GitHub Pages (free, public URL)
1. Create a new repo on GitHub (e.g. `agriconvert`)
2. Upload all files to the repo root
3. Go to Settings → Pages → Source: main branch / root
4. App live at: `https://yourusername.github.io/agriconvert/`
5. Share URL via WhatsApp to workers

## Features — v1.0
### 📐 Converters
- Area: m², Hectare, Acre, Rood, Square Pole, Sq Ft, 坪, 市亩, Relong
- Length: mm, cm, m, km, Inch, Foot, Yard, Chain, Rod, Link
- Weight: g, kg, Tonne, oz, lb, Bag(25kg), Bag(50kg), Pikul
- Volume: ml, cc, L, m³, fl oz, Pint, Quart, Gallon US/UK

### 🧪 Calculators
- Spray Mix: dose rate × tank size → product per tank
- Fertilizer: kg/ha or kg/tree → total kg + bags needed + cost
- Dilution: target % or label rate → product + water volumes

### ⚙️ Settings
- Unit system (Malaysian / Metric / Imperial / Mixed)
- Conversion history (last 20, clearable)
- Offline ready via service worker
