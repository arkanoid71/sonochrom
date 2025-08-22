# 🛠 Musical Painting — Developer Guide

Musical Painting is an open-source **Electron + React + Vite** app that turns live audio into generative visuals.

---

## 📋 Prerequisites

- macOS 12+ (tested on Apple Silicon, macOS Sequoia 15.6)
- Node.js v18+
- npm v9+

---

## 🚧 Getting Started

```bash
# Clone repository
git clone https://github.com/your-username/musical-painting.git
cd musical-painting

# Install dependencies
npm install

# Run in dev mode (hot reload)
npm run dev
```

This will:
- Start Vite dev server on `http://localhost:5173`
- Launch Electron pointing to that dev server

---

## 📦 Building

```bash
# Clean previous builds
rm -rf dist dist-electron

# Build renderer + Electron main
npm run build

# Package macOS app + DMG
npm run electron:build
```

The packaged `.app` and `.dmg` appear in `dist/`.

---

## 📂 Project Structure

```
musical-painting/
├── electron/               # Electron main & preload
│   ├── main.ts
│   └── preload.ts
├── src/                    # React renderer
│   ├── App.tsx             # Main app (canvas, audio, UI)
│   ├── main.tsx            # React entry
│   └── index.css           # Tailwind styles
├── public/                 # Static assets
├── package.json            # Scripts, deps, electron-builder config
├── vite.config.ts          # Vite config
├── tsconfig.json           # TS config (renderer)
├── tsconfig.electron.json  # TS config (Electron, CJS)
└── entitlements.mac.plist  # macOS sandbox entitlements
```

---

## 🔑 Implementation Details

- **Audio Analysis**
  - Uses Web Audio API (`AnalyserNode`) for RMS and spectrum.
  - Pitch estimated with autocorrelation (ACF).
- **Graphics**
  - Canvas 2D shapes responsive to loudness, pitch, brightness.
  - Shape families controlled via dropdown.
- **Export**
  - `canvas.toBlob()` → PNG export.
  - `canvas.captureStream()` + `MediaRecorder` → 10s WebM recording.
- **Electron**
  - Runs in **CommonJS** mode for `__dirname` compatibility.
  - In packaged builds, loads `dist/index.html` from inside `app.asar`.

---

## 📜 Scripts

- `npm run dev` → Dev mode with hot reload.
- `npm run build` → Build renderer & Electron main.
- `npm run electron:build` → Build and package `.app` + `.dmg`.

---

## 🧩 Customization

- Add palettes in `App.tsx` (`const palettes`).
- Add shapes in the `if (family === …)` drawing block.
- Tweak audio-reactivity via RMS or pitch scaling.

---

## 🚀 Next Steps

- Add duration selector for WebM (5s, 10s, 30s).
- Add high-res export (4K PNG / WebM).
- Cross-platform packaging (Windows/Linux).
- Explore ML-based style transfer for painterly visuals.
