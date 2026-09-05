# 🌐 God's Eye View - Ready to Start

> **A spy satellite simulator in your browser — except the data is real.**

This repository contains **complete setup instructions** for running **God's Eye View** — a live 3D globe with real-time aircraft, ships, satellites, earthquakes, CCTV cameras, and more.

**Status:** ✅ Ready to clone and run. Zero configuration needed.

---

## 📚 Documentation

Choose your setup style:

### 🚀 **[QUICK_START.md](QUICK_START.md)** (5 minutes)
**The fastest way to get running.**
- Clone → Install → Start
- First things to try
- Common keyboard shortcuts
- Optional API key upgrades

### 📋 **[SETUP_INSTRUCTIONS.md](SETUP_INSTRUCTIONS.md)** (Step-by-step)
**Detailed walkthrough for beginners.**
- System requirements
- Step-by-step installation
- First-run experience
- Keyboard shortcuts
- Adding API keys
- Troubleshooting guide

### ✅ **[INSTALLATION_CHECKLIST.md](INSTALLATION_CHECKLIST.md)** (Validation)
**Ensure everything works.**
- Pre-installation checklist
- Step-by-step validation
- First-run validation
- Optional key setup
- Troubleshooting flowchart
- Performance baselines

---

## ⚡ TL;DR — Get Running in 30 Seconds

```bash
# Prerequisites: Node.js 24.x or 26.x

# 1. Clone
git clone https://github.com/bilawalsidhu/gods-eye-view.git
cd gods-eye-view

# 2. Install
npm ci

# 3. Start
npm run dev

# 4. Open browser
# → http://localhost:4173
```

**That's it.** The app loads with live aircraft, ships, satellites, and more — all free, no keys required.

---

## 🎯 What You Get

**Live Data (All Free)**
- ✈️ 11,000+ live aircraft in real-time
- 🚢 Live ship positions worldwide
- 🛰️ 838 satellites (Starlink, ISS, etc.)
- 🌍 Earthquakes (last 24 hours)
- 🔥 Active fires (NASA FIRMS)
- 📹 Public CCTV cameras projected into 3D
- 📻 750+ radio stations geolocated
- 🚀 Rocket launches & orbital mechanics

**Capabilities (No Keys Needed)**
- 🌐 3D photorealistic globe (Esri satellite)
- 🎛️ Cockpit view (ride along with aircraft)
- 👁️ Multiple visual styles (CRT, NVG, FLIR thermal)
- 📊 Intelligence HUD
- 🖊️ Annotation whiteboard
- 🎥 Cinematic camera controls
- 🔗 Share links (serialize view + target)

**Optional Upgrades (Add Keys)**
- 🗺️ Google Photorealistic 3D cities
- 🎙️ Voice control powered by OpenAI
- 📍 Place search and routing
- 🚦 Live traffic congestion
- 📊 Analytics and heatmaps

---

## 🚀 Quick Links

| What You Want | Link |
|---|---|
| **Run it now** | [QUICK_START.md](QUICK_START.md) |
| **Step-by-step guide** | [SETUP_INSTRUCTIONS.md](SETUP_INSTRUCTIONS.md) |
| **Validate setup** | [INSTALLATION_CHECKLIST.md](INSTALLATION_CHECKLIST.md) |
| **Original project** | [github.com/bilawalsidhu/gods-eye-view](https://github.com/bilawalsidhu/gods-eye-view) |
| **Live demo** | [maptheworld.ai](https://maptheworld.ai/) |
| **YouTube tutorials** | [@bilawalsidhu](https://youtube.com/@bilawalsidhu) |

---

## 💻 System Requirements

- **OS:** Windows, macOS, or Linux
- **Node.js:** v24.14.0+ or v26.x (NOT v25.x)
- **npm:** 10.x or later (comes with Node.js)
- **RAM:** 4GB minimum, 8GB recommended
- **Disk:** ~500MB for dependencies
- **Internet:** Required for live data

---

## 🎮 First 5 Minutes

1. **Run:** `npm run dev`
2. **Open:** `http://localhost:4173`
3. **Select Mission:** "Live Contacts"
4. **Watch:** 11,000+ aircraft appear on globe
5. **Click:** Any aircraft
6. **Press `C`:** Enter cockpit view
7. **Press `1-7`:** Switch visual styles
8. **Press Esc:** Exit
9. **Press `H`:** Toggle HUD
10. **Explore:** Click other objects, try other missions

---

## 🔑 Add API Keys (Optional)

**All free or eligible for free tier:**

1. **Cesium ion** (recommended first)
   - What: Google Photorealistic 3D + terrain
   - Cost: Free (eligible non-commercial)
   - Get it: [cesium.com/ion](https://cesium.com/ion)

2. **OpenAI** (for voice control)
   - What: Voice commands + AI summaries
   - Cost: ~$0.02/minute (metered)
   - Get it: [platform.openai.com](https://platform.openai.com)

3. **Others** (all optional)
   - Google Maps, AISStream, NASA FIRMS, TomTom
   - See [QUICK_START.md](QUICK_START.md) for full list

**How to add:**
1. Click **POWER UP** chip (bottom-right)
2. Go to **Provider Settings**
3. Paste key
4. Click **SAVE KEYS**
5. App restarts automatically

---

## 🎙️ Voice Control (Requires OpenAI Key)

Once you add an OpenAI key:

```
"Take me to Tokyo"
"Show me military helicopters in circles"
"Outline the state of Texas"
"How many flights are over the US?"
"Track that plane"
"Enter cockpit mode"
"Fly the route we just drew"
```

The AI agent understands live scene context and can answer questions about what it sees.

---

## ⌨️ Keyboard Shortcuts

| Key | Action |
|-----|--------|
| `1`–`7` | Cycle visual styles |
| `C` | Cockpit view (when tracking) |
| `H` | Toggle HUD |
| `D` | Toggle detection overlay |
| `Esc` | Exit cockpit |
| `?` | Show all shortcuts |
| `0` | Fullscreen |

---

## 📁 What's Inside

```
Original Project: bilawalsidhu/gods-eye-view
├── src/
│   ├── main.js          # Bootstrap & layer registration
│   ├── ui.js            # UI panels and controls
│   ├── voice/           # OpenAI Realtime + voice tools
│   └── data/            # Live data layers
├── index.html           # Main page
├── style.css            # Styles (256KB)
├── vite.config.js       # Dev server config
├── package.json         # Dependencies
└── scripts/             # Utility scripts
```

---

## ❓ FAQ

**Q: Do I need API keys to start?**
A: No. The app runs completely free with 11,000+ live aircraft, ships, satellites, and more. Keys unlock optional features (Google 3D, voice control).

**Q: Which Node.js version?**
A: 24.14.0 or later, or 26.x. NOT 25.x (end-of-life).

**Q: Can I run this on a server?**
A: Yes. By default it binds to localhost (secure). To share on LAN: `HOST=0.0.0.0 npm run dev` (only on trusted networks).

**Q: How much data does it use?**
A: Varies by features. Aircraft updates every 15-30 seconds. Live feeds are optimized. Expect 100-500MB/day depending on usage.

**Q: Can I add my own data?**
A: Yes. The code is open source. See [CONTRIBUTING.md](https://github.com/bilawalsidhu/gods-eye-view/blob/main/CONTRIBUTING.md).

**Q: What if I get stuck?**
A: See troubleshooting in [SETUP_INSTRUCTIONS.md](SETUP_INSTRUCTIONS.md) or open an issue in [the main repo](https://github.com/bilawalsidhu/gods-eye-view/issues).

---

## 🔗 Resources

- **[Main Repository](https://github.com/bilawalsidhu/gods-eye-view)** — Original project
- **[Data Sources](https://github.com/bilawalsidhu/gods-eye-view/blob/main/DATA_SOURCES.md)** — Provider details
- **[Security Guide](https://github.com/bilawalsidhu/gods-eye-view/blob/main/SECURITY.md)** — Key management
- **[Contributing](https://github.com/bilawalsidhu/gods-eye-view/blob/main/CONTRIBUTING.md)** — Development guide
- **[YouTube](https://youtube.com/@bilawalsidhu)** — Video tutorials
- **[Homepage](https://maptheworld.ai/)** — Marketing site

---

## 📄 License

MIT License — See [LICENSE](https://github.com/bilawalsidhu/gods-eye-view/blob/main/LICENSE)

---

## 👏 Credits

- **Original Creator:** [Bilawal Sidhu](https://github.com/bilawalsidhu)
- **Co-Maintainer:** [Sameh Khamis](https://github.com/samehkhamis)
- **Organization:** [Halfpixel](https://halfpixel.ai)

---

## 🌍 Start Exploring

```bash
npm run dev
# → http://localhost:4173
```

**No place left behind.** 🌐
