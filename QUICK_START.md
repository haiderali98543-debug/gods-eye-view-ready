# 🚀 God's Eye View - Ready to Start

**Your project is ready to run!**

## ⚡ One-Minute Setup

### Prerequisites
- **Node.js 24.x** (24.14.0 or later) or **26.x**
- **Git** (to clone the original repo)

### Step 1: Clone the Original Repository
```bash
git clone https://github.com/bilawalsidhu/gods-eye-view.git
cd gods-eye-view
```

### Step 2: Install Dependencies
```bash
npm ci
```

### Step 3: Check System Setup
```bash
npm run doctor
```
This validates Node.js version, npm, and available provider routes.

### Step 4: Start the Development Server
```bash
npm run dev
```

### Step 5: Open in Browser
**Navigate to:** `http://localhost:4173`

The app loads in seconds. You'll see a first-run panel with mission options.

---

## 🎯 First Things to Try (No Keys Needed!)

1. **Select a Mission**
   - **Live Contacts** → See 11,000+ aircraft in real-time
   - **Space Missions** → Watch rocket launches
   - **Environmental** → Track fires and earthquakes
   - **Explore Manually** → Free roaming

2. **Interact with the Globe**
   - **Click any aircraft** → See its flight path
   - **Press `C`** → Cockpit mode (ride along!)
   - **Press `1-7`** → Cycle visual styles (CRT, NVG, FLIR thermal)
   - **Press `H`** → Toggle HUD (heads-up display)
   - **Press `D`** → Toggle detection mesh
   - **Press `Esc`** → Exit cockpit

3. **Explore Layers** (all free, no keys!)
   - ✈️ Live Flights (11,000+ aircraft)
   - 🚢 Live Ships (AISStream)
   - 🛰️ Satellites (838-object catalog)
   - 🌍 Earthquakes (last 24h, USGS)
   - 🔥 Active Fires (NASA FIRMS)
   - 📻 Global Radio (750+ stations)
   - 📹 CCTV Mesh (public cameras projected into 3D)
   - 🚀 Space Missions (rocket launches)

---

## 🔑 Upgrade with API Keys (Optional)

Keys unlock photorealistic 3D and voice control. **Add them inside the app:**

1. **Click POWER UP** (bottom-right corner)
2. **Go to Provider Settings**
3. **Paste your keys and click SAVE KEYS**
4. **App restarts automatically**

### Recommended Keys (In Order)

| Key | What It Does | Cost | Get It |
|-----|---|---|---|
| **Cesium ion** | Google Photorealistic 3D + terrain | Free (eligible non-commercial) | [cesium.com/ion](https://cesium.com/ion) |
| **Google Maps** | Direct Google 3D + place search | Metered | [Google Cloud Console](https://console.cloud.google.com) |
| **OpenAI** | Voice control + AI summaries | Metered | [OpenAI Platform](https://platform.openai.com) |
| **AISStream** | Live global ships | Free signup | [aisstream.io](https://aisstream.io) |
| **NASA FIRMS** | Live active fires layer | Free | [firms.modaps.eosdis.nasa.gov](https://firms.modaps.eosdis.nasa.gov/api/map_key/) |
| **TomTom** | Live traffic congestion | Free tier | [developer.tomtom.com](https://developer.tomtom.com) |

---

## 🎙️ Voice Control (Requires OpenAI Key)

Once you add an OpenAI key:

1. **Click GEV MIC**
2. **Grant microphone permission**
3. **Say commands like:**
   - *"Take me to Tokyo"*
   - *"Show me the planes overhead"*
   - *"Outline the state of Texas"*
   - *"How many flights are over the US?"*
   - *"Track that plane"*
   - *"Enter cockpit mode"*

The agent understands live scene context and can answer questions about what's visible.

---

## 📁 Project Structure

```
gods-eye-view/
├── src/
│   ├── main.js              # Bootstrap & layer registration
│   ├── ui.js                # UI panels, controls, styles
│   ├── hud.js               # Intelligence HUD + AI summaries
│   ├── voice/               # OpenAI Realtime + 28 voice tools
│   └── data/                # Live layers (flights, ships, satellites, etc.)
├── config/                  # Configuration files
├── public/                  # Static assets
├── index.html               # Main HTML entry
├── style.css                # Styles
├── vite.config.js           # Vite config + dev server
├── package.json             # Dependencies
└── scripts/
    ├── setup-doctor.mjs     # System check
    └── dev-fresh.sh         # macOS Keychain launcher
```

---

## 🛠️ Common Commands

```bash
# Start dev server (most common)
npm run dev

# Start with full Keychain support (macOS only)
./scripts/dev-fresh.sh

# Check system setup
npm run doctor

# Build for production
npm run build

# Run tests
npm run test

# Preview production build
npm run preview
```

---

## 🌐 Accessing from Other Devices (LAN)

By default, the server runs on **localhost only** (secure).

To share on your LAN:

```bash
HOST=0.0.0.0 npm run dev
```

⚠️ **Warning:** This exposes your API keys to everyone on the network. Only use on trusted networks.

---

## 🔒 Security Notes

- **Your API keys never leave your machine** (except to provider APIs)
- **All keys are server-side** (except Google Maps & Cesium ion, which are client-restricted)
- **No data is stored** — everything is real-time
- **Keys are stored locally** in `.env` (Git-ignored) or Pinokio's ENVIRONMENT file
- See [SECURITY.md](https://github.com/bilawalsidhu/gods-eye-view/blob/main/SECURITY.md) for details

---

## 🚀 What's Running

- **Frontend:** Vanilla JavaScript + CesiumJS + Vite
- **Backend:** Dev server (Node.js) with API proxies
- **3D Engine:** CesiumJS with Google Photorealistic 3D tiles
- **Data Sources:** OpenSky (flights), AIS (ships), CelesTrak (satellites), USGS (earthquakes), NASA FIRMS (fires), Launch Library (launches), and more

---

## 📚 Next Steps

1. **Run it:** `npm run dev` → `http://localhost:4173`
2. **Explore:** Pick a mission and play
3. **Add keys:** Click POWER UP for enhanced features
4. **Hack it:** The code is completely open — modify layers, add data sources, etc.
5. **Share:** Click any target → **Share Links** serializes your view into a URL

---

## 🎓 Learning Path

**5 minutes:** Turn on Flights, click an aircraft, press `C` for cockpit view.

**15 minutes:** Try different visual styles (`1-7`), click a ship, find CCTV cameras nearby.

**30 minutes:** Add a Cesium ion key for Google Photorealistic 3D, explore a city at street level.

**1 hour:** Add an OpenAI key, try voice commands, ask questions about what you see.

**∞ hours:** Extend it with your own data layers, API sources, and features.

---

## ❓ Troubleshooting

### Port Already in Use
```bash
PORT=5173 npm run dev
```

### Node Version Error
```bash
node --version  # Must be 24.14.0+ or 26.x
```

### Slow Startup
Clear Vite cache:
```bash
rm -rf node_modules/.vite
npm run dev
```

### Provider Keys Not Working
Run `npm run doctor` to verify provider routes are accessible.

---

## 📖 Full Documentation

- **[Main README](https://github.com/bilawalsidhu/gods-eye-view/blob/main/README.md)** — Complete guide
- **[Data Sources](https://github.com/bilawalsidhu/gods-eye-view/blob/main/DATA_SOURCES.md)** — Provider details
- **[Contributing](https://github.com/bilawalsidhu/gods-eye-view/blob/main/CONTRIBUTING.md)** — Development guide
- **[Security](https://github.com/bilawalsidhu/gods-eye-view/blob/main/SECURITY.md)** — Key & privacy info
- **[YouTube Series](https://youtube.com/playlist?list=PL6qSg2I-7_koPbDnSMo0QeeHX_RknA2uv)** — Walkthrough videos

---

## 🌍 Welcome Aboard

**You're running a live intelligence console for planet Earth.**

No place left behind. 🌐
