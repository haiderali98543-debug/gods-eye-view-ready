# 📋 Detailed Setup Instructions

## System Requirements

- **Operating System:** Windows, macOS, or Linux
- **Node.js:** v24.14.0+ or v26.x (NOT v25.x)
- **npm:** Comes with Node.js
- **RAM:** 4GB minimum (8GB recommended)
- **Disk Space:** ~500MB for dependencies
- **Internet:** Required for live data feeds

## Step-by-Step Installation

### 1. Verify Node.js

```bash
node --version
npm --version
```

**Expected output:**
```
v24.14.0  (or v26.x)
10.x.x    (or later)
```

If you don't have Node.js or have the wrong version:
- **macOS:** `brew install node@24` or download from [nodejs.org](https://nodejs.org)
- **Windows:** Download from [nodejs.org](https://nodejs.org)
- **Linux:** `sudo apt install nodejs npm` or use [nvm](https://github.com/nvm-sh/nvm)

### 2. Clone the Repository

```bash
git clone https://github.com/bilawalsidhu/gods-eye-view.git
cd gods-eye-view
```

### 3. Install Dependencies

```bash
npm ci
```

**What this does:**
- Downloads and installs exact package versions (from `package-lock.json`)
- Sets up CesiumJS, Vite, sharp, puppeteer, and other dependencies
- Takes 2-5 minutes depending on internet speed

**Output should end with:** ✅ `added X packages`

### 4. Run System Check

```bash
npm run doctor
```

**This validates:**
- ✅ Node.js version compatibility
- ✅ npm readiness
- ✅ Provider API routes (flights, ships, satellites, etc.)
- ✅ Environment configuration

**Troubleshooting:**
If you see errors, check:
- Internet connection (live data sources need access)
- Node.js version matches requirements
- npm is properly installed

### 5. Start Development Server

```bash
npm run dev
```

**Expected output:**
```
  VITE v6.x.x  ready in XXX ms

  ➜  Local:   http://localhost:4173/
  ➜  press h + enter to show help
```

### 6. Open in Browser

**Click or copy-paste:**
```
http://localhost:4173
```

The browser should open automatically. If not, manually navigate to the URL above.

---

## First-Run Experience

On first load, you'll see:

**1. Mission Selection Panel**
- 🟢 **Live Contacts** — 11,000+ live aircraft
- 🟢 **Space Missions** — Rocket launches & orbital mechanics
- 🟢 **Environmental** — Fires, earthquakes, weather
- 🟢 **Explore Manually** — Free roaming mode

Click any mission to start. All require **no API keys**.

**2. The 3D Globe Loads**
- Takes 3-8 seconds
- Shows Esri satellite imagery (free)
- Displays selected live data layer

**3. Start Exploring**
- Drag to pan
- Scroll to zoom
- Click objects to track them
- Press `?` for keyboard shortcuts

---

## Keyboard Shortcuts (First 5 Minutes)

| Key | Action |
|-----|--------|
| `1`–`7` | Cycle visual styles (CRT, NVG, FLIR thermal, etc.) |
| `C` | Enter/exit cockpit view (when tracking) |
| `H` | Toggle HUD (intelligence display) |
| `D` | Toggle detection overlay |
| `Esc` | Exit cockpit / reset view |
| `?` | Show all keyboard shortcuts |
| `0` | Toggle full-screen |

---

## Adding API Keys (Optional)

### Inside the App (Easiest)

1. **Look for POWER UP chip** (bottom-right corner)
2. **Click it** → Opens "Provider Settings" panel
3. **Paste your key** into the field
4. **Click SAVE KEYS**
5. **App restarts** automatically with new capability

### Via Environment File (Advanced)

**Create or edit `.env` in the project root:**

```bash
# Copy the example
cp .env.example .env

# Edit .env and add your keys
nano .env  # or use your preferred editor
```

**Then restart:**
```bash
npm run dev
```

---

## macOS with Keychain (Advanced)

Store keys securely in macOS Keychain:

```bash
# Add keys to Keychain (interactive)
security add-generic-password -U -s "google-maps-api" -a "api-key" -w
security add-generic-password -U -s "cesium-ion" -a "token" -w
security add-generic-password -U -s "openai-api" -a "api-key" -w

# Launch with Keychain integration
./scripts/dev-fresh.sh
```

The script auto-reads keys from Keychain and passes them to the dev server.

---

## Troubleshooting

### Error: "Node version not supported"

**Solution:**
```bash
# Check your version
node --version

# Install correct version
node v24.14.0 from nodejs.org
# OR use nvm (recommended):
nvm install 24.14.0
nvm use 24.14.0
```

### Error: "Cannot find module 'cesium'"

**Solution:**
```bash
# Reinstall dependencies
rm -rf node_modules package-lock.json
npm ci
```

### Port 4173 Already in Use

**Solution:**
```bash
# Use a different port
PORT=5173 npm run dev

# Or find what's using the port
# macOS/Linux:
lsof -i :4173
# Windows:
netstat -ano | findstr :4173
```

### Very Slow Startup (>10 seconds)

**Solution:**
```bash
# Clear Vite cache
rm -rf node_modules/.vite

# Cold start dev server
npm run dev
```

### API Keys Not Working

**Solution:**
1. Run `npm run doctor` to verify provider routes
2. Check internet connection
3. Verify key is correctly copied (no extra spaces)
4. Restart dev server after adding key
5. Check browser console for errors (`F12` → Console tab)

### Blank Screen After Loading

**Solution:**
1. Open browser console: `F12`
2. Look for red error messages
3. Common issues:
   - JavaScript disabled (enable it)
   - Old browser (use Chrome/Firefox/Safari latest)
   - Ad blocker interfering (whitelist `localhost:4173`)

---

## Next Steps After Setup

### 5-Minute Tutorial
1. Select "Live Contacts" mission
2. Watch aircraft appear on the globe
3. Click one to select it
4. Press `C` to enter cockpit view
5. Press `1-7` to switch visual styles

### Add Your First Key
1. Get free [Cesium ion token](https://cesium.com/ion)
2. Click POWER UP → Provider Settings
3. Paste token → Save Keys
4. Reload page (or wait for auto-restart)
5. Enjoy Google Photorealistic 3D cities!

### Enable Voice Control
1. Get [OpenAI API key](https://platform.openai.com)
2. Add via POWER UP panel
3. Click GEV MIC
4. Grant microphone permission
5. Say: *"Take me to London"*

### Learn the Codebase
- Open `src/main.js` — see layer registration
- Open `src/data/` — explore each live layer
- Open `src/voice/` — see voice command tools
- Read [CONTRIBUTING.md](https://github.com/bilawalsidhu/gods-eye-view/blob/main/CONTRIBUTING.md)

---

## Staying Updated

```bash
# Pull latest changes
git pull origin main

# Reinstall dependencies (in case they changed)
npm ci

# Run doctor to check everything
npm run doctor

# Restart dev server
npm run dev
```

---

## Getting Help

- **[GitHub Issues](https://github.com/bilawalsidhu/gods-eye-view/issues)** — Report bugs
- **[Data Sources Guide](https://github.com/bilawalsidhu/gods-eye-view/blob/main/DATA_SOURCES.md)** — Provider info
- **[YouTube Channel](https://youtube.com/@bilawalsidhu)** — Tutorials
- **[Main README](https://github.com/bilawalsidhu/gods-eye-view/blob/main/README.md)** — Complete reference

---

**You're all set! 🚀 Run `npm run dev` and start exploring the world.**
