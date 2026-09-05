# ✅ Installation Checklist

Use this checklist to ensure your God's Eye View setup is complete and working.

## Prerequisites (Before You Start)

- [ ] **Node.js 24.x or 26.x installed**
  ```bash
  node --version  # Should show v24.14.0+ or v26.x
  ```

- [ ] **npm installed** (comes with Node.js)
  ```bash
  npm --version   # Should show 10.x or later
  ```

- [ ] **Git installed**
  ```bash
  git --version   # Should show git version 2.x or later
  ```

- [ ] **Internet connection available** (for live data feeds)

- [ ] **4GB+ RAM available** (8GB recommended)

---

## Installation Steps

### 1. Clone Repository

```bash
git clone https://github.com/bilawalsidhu/gods-eye-view.git
cd gods-eye-view
```

- [ ] Repository cloned successfully
- [ ] You're inside the `gods-eye-view` directory
- [ ] You see `package.json`, `src/`, `index.html`, etc.

### 2. Install Dependencies

```bash
npm ci
```

- [ ] Command completed without errors
- [ ] No red `ERR!` messages
- [ ] Saw message: `added X packages`
- [ ] `node_modules/` directory exists

### 3. Run System Check

```bash
npm run doctor
```

- [ ] Command ran successfully
- [ ] ✅ Node.js version validated
- [ ] ✅ npm validated
- [ ] ✅ Provider routes checked
- [ ] No critical errors reported

### 4. Start Development Server

```bash
npm run dev
```

- [ ] Dev server started
- [ ] Saw: `VITE v6.x.x ready in XXX ms`
- [ ] Saw: `Local: http://localhost:4173/`
- [ ] No errors in terminal
- [ ] Server is running (terminal shows waiting for requests)

### 5. Open in Browser

**Navigate to:** `http://localhost:4173/`

- [ ] Browser opens automatically (or you can manually navigate)
- [ ] Page loads in 3-8 seconds
- [ ] You see the 3D globe
- [ ] First-run panel appears with mission options
- [ ] No blank screens or JavaScript errors

---

## First-Run Validation

### Globe Displays Correctly

- [ ] 3D globe is visible
- [ ] Esri satellite imagery loads
- [ ] Zoom in/out works (scroll wheel or pinch)
- [ ] Drag to pan works
- [ ] No purple/black terrain tiles visible

### Live Data Loads

Click any mission and wait 5 seconds:

- [ ] **Live Contacts:** 11,000+ aircraft appear as small glyphs
- [ ] **Space Missions:** Satellites and launch info visible
- [ ] **Environmental:** Earthquakes, fires, weather visible
- [ ] Layers list on left shows active data sources

### Controls Work

- [ ] Press `1` → Screen style changes to CRT
- [ ] Press `2` → Changes to another style
- [ ] Press `H` → HUD appears/disappears
- [ ] Press `D` → Detection overlay toggles
- [ ] Press `?` → Keyboard shortcuts appear
- [ ] Esc → Exits any overlay

### Interactions Function

- [ ] Click any aircraft → It highlights
- [ ] Click again → Selection info appears
- [ ] Press `C` → Enter cockpit view (if tracking)
- [ ] Press Esc → Exit cockpit
- [ ] POWER UP chip visible (bottom-right)

---

## Optional: Add API Keys

### Get a Cesium ion Token (Recommended First Key)

- [ ] Sign up at [cesium.com/ion](https://cesium.com/ion)
- [ ] Verify email
- [ ] Create new access token
- [ ] Copy token to clipboard

### Add Key via App

- [ ] Click **POWER UP** chip (bottom-right)
- [ ] Click **Provider Settings**
- [ ] Find **Cesium ion** field
- [ ] Paste token
- [ ] Click **SAVE KEYS**
- [ ] App restarts automatically
- [ ] Google Photorealistic 3D loads (cities appear hyper-realistic)

---

## Troubleshooting Checklist

### If Dev Server Won't Start

- [ ] Check Node.js version: `node --version` → must be 24.14.0+ or 26.x
- [ ] Delete `node_modules/`: `rm -rf node_modules`
- [ ] Reinstall: `npm ci`
- [ ] Try again: `npm run dev`

### If Port 4173 Is in Use

- [ ] Use different port: `PORT=5173 npm run dev`
- [ ] Or kill process using port:
  ```bash
  # macOS/Linux
  lsof -i :4173 | grep LISTEN | awk '{print $2}' | xargs kill -9
  
  # Windows
  netstat -ano | findstr :4173
  taskkill /PID <PID> /F
  ```

### If Globe Doesn't Load

- [ ] Hard refresh browser: `Cmd+Shift+R` (macOS) or `Ctrl+Shift+R` (Windows/Linux)
- [ ] Clear browser cache
- [ ] Try private/incognito window
- [ ] Check internet connection
- [ ] Look for JavaScript errors: Press `F12` → Console tab

### If Live Data Doesn't Appear

- [ ] Check internet connection
- [ ] Run `npm run doctor` to verify provider routes
- [ ] Wait 10 seconds (data can take time to load)
- [ ] Check browser console for errors (`F12`)
- [ ] Refresh page (Cmd+R or Ctrl+R)

### If Voice Control Doesn't Work

- [ ] Ensure OpenAI API key is added
- [ ] Check browser microphone permissions (site settings)
- [ ] Try in private/incognito window (permission cache issue)
- [ ] Check browser console for errors
- [ ] Verify internet connection

---

## Performance Baseline

Expected timings on modern hardware:

- [ ] `npm ci` install: 2-5 minutes
- [ ] `npm run doctor`: 5-15 seconds
- [ ] `npm run dev` startup: 3-10 seconds
- [ ] Browser page load: 3-8 seconds
- [ ] Aircraft appear: Within 5 seconds of mission select
- [ ] Cockpit view: Instant (already rendered)
- [ ] Style switch (1-7 keys): Instant (<100ms)

If significantly slower, check:
- [ ] Disk I/O performance
- [ ] RAM availability
- [ ] Network speed
- [ ] Background processes consuming CPU

---

## System Info (For Support)

If you need help, have this info ready:

```bash
# Gather system information
node --version
npm --version
git --version
uname -a              # macOS/Linux
ver                   # Windows
df -h                 # Disk space
free -h               # RAM (Linux)
vm_stat               # RAM (macOS)
```

---

## Success!

If all boxes are checked, your God's Eye View installation is **complete and ready to use**.

**Next steps:**

1. Explore live data without keys
2. Add Cesium ion token for Google 3D
3. Add OpenAI key for voice control
4. Read [Contributing Guide](https://github.com/bilawalsidhu/gods-eye-view/blob/main/CONTRIBUTING.md) to extend it
5. Watch [YouTube tutorials](https://youtube.com/@bilawalsidhu)

**Happy exploring! 🌍**
