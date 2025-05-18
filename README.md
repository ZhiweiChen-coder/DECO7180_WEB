# ⚡ **Viron – EV Awareness Platform**

*Helping Australians make confident, data‑driven decisions about electric vehicles.*

---

## 📑 Table of Contents

1. [About Viron](#about-viron)
2. [Live Demo](#live-demo)
3. [Key Features](#key-features)
4. [Project Structure](#project-structure)
5. [Getting Started](#getting-started)
6. [Configuration](#configuration)

---

## About Viron

Viron is a **static web toolkit** designed for coursework & community outreach that demystifies electric‑vehicle ownership in Australia. The site aggregates **real‑time charger locations**, explains **financial incentives**, busts **common myths**, and provides **interactive calculators** so that visitors can quickly see whether an EV fits their lifestyle.

> **Goal:** Accelerate EV adoption by lowering the *information cost* for everyday drivers.

---

## Live Demo

The project is 100 % client‑side, so you can simply open **`index.html`** in any modern browser. For a smoother experience (and to avoid CORS when calling the Open Charge Map API) we recommend serving the files via a tiny local server:

```bash
npx serve .            # or python -m http.server 8080
open http://localhost:8080
```

---

## Key Features

| Page / Tool                                              | What it does                                                                                                                      |
| -------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| **Landing (`index.html`)**                               | Hero intro, mission statement, high‑level EV stats & call‑to‑action buttons.                                                      |
| **Nation‑wide Charging Map (`Charging_Map.html`)**       | Live Leaflet map fed by the **Open Charge Map** API with suburb / postcode search, GPS centring & charger‑type filtering.         |
| **Benefits & Myths (`Benefits_myths.html`)**             | Card‑grid explaining environmental, financial & performance benefits while debunking common misconceptions.                       |
| **EV Challenges (`EV_challenges.html`)**                 | Honest look at current barriers (range anxiety, upfront cost, infrastructure) with data‑driven context.                           |
| **Incentives & Energy Cost Savings (`Incentives.html`)** | Up‑to‑date state & federal rebates **plus** our renamed **Energy Cost Savings Calculator** that compares ICE vs EV running costs. |
| **FAQ & About (`FAQ_about.html`)**                       | Collapsible FAQ accordion, team bio & contact details.                                                                            |
| **Legal (`terms.html`, `privacy.html`, `cookies.html`)** | Plain‑English Terms of Service, Privacy Policy & Cookie settings.                                                                 |

All pages share **`style.css`** (responsive Tailwind‑like design tokens) and **`main.js`** (navigation toggle, map logic, calculators).

---

## Project Structure

```
Viron/
├── index.html                # Landing page
├── Charging_Map.html         # Interactive charger map
├── Benefits_myths.html       # EV benefits vs myths
├── EV_challenges.html        # Barriers to EV adoption
├── Incentives.html           # Incentives & Energy Cost Savings Calculator
├── FAQ_about.html            # FAQ & About page
├── terms.html                # Terms of Service
├── privacy.html              # Privacy Policy
├── cookies.html              # Cookie preferences modal
├── style.css                 # Global styles & tokens
├── main.js                   # Core JavaScript (map, calculators, nav)
└── README.md                 # You are here 📖
```

---

## Getting Started

1. **Clone** the repo or download the ZIP.
2. *(Optional but recommended)* Serve the folder locally:

   ```bash
   npm install -g serve   # once
   serve .
   ```
3. Browse to `http://localhost:3000` (or the port `serve` prints).
4. Explore each page via the nav bar or the quick links below the hero.

> **Note:** All API calls use HTTPS and require no secret keys.

---

## Configuration

| Setting                         | Where                          | Details                                                                                                     |
| ------------------------------- | ------------------------------ | ----------------------------------------------------------------------------------------------------------- |
| **Map tile provider**           | `main.js` → `L.tileLayer(...)` | Currently using free *Carto Voyager* tiles. Replace the URL/template or add a Mapbox token if desired.      |
| **Open Charge Map** endpoint    | `main.js` → `fetch(...)`       | Default public endpoint returns JSON of nearby chargers. The call respects browser geolocation permissions. |
| **Units & defaults**            | `main.js` constants            | Adjust default fuel price, electricity rate, or annual km in the calculator section.                        |
| **Brand colours & breakpoints** | `style.css` root variables     | Swap out `--primary-color`, `--accent-color`, etc., to match your branding.                                 |

---

> *Built for UQ DECO7180 by Team **Viron** – because the future of transport should be clean, affordable & transparent.*
