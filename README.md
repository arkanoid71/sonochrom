# 🎨 Musical Painting

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Electron](https://img.shields.io/badge/Electron-31.x-blue.svg)](https://www.electronjs.org/)
[![React](https://img.shields.io/badge/React-18.x-61dafb.svg)](https://reactjs.org/)

**Musical Painting** turns your microphone input into **generative artwork**.  
Play an instrument, sing, or just make sounds — and watch your audio become dynamic, colorful visuals in real time.

---

## ✨ Features

- 🎤 **Live microphone input** (voice or instrument)
- 🎨 Multiple **color palettes** (Vibrant, Pastels, Monochrome)
- 🌀 **Shape families**:
  - Blobs
  - Bursts
  - Polygons
  - Spiral
  - Lissajous
  - Grid
  - Wave
  - Ribbons
- 💾 Export your art:
  - Save stills as **PNG**
  - Record short **WebM video clips (10s)**
- ⌨️ Keyboard shortcuts:
  - `S` → Save PNG
  - `R` → Record WebM
  - `⌘+⌥+I` → Open Developer Tools

---

## 📸 Screenshots

*(Add some screenshots or GIF demos here)*

---

## 📖 Documentation

- [User Guide](./USER_GUIDE.md) → Installation & how to use the app  
- [Developer Guide](./DEVELOPER_GUIDE.md) → Setup, build, and contribute  

---

## 🚀 Quick Start (Developers)

```bash
# Clone the repo
git clone https://github.com/your-username/musical-painting.git
cd musical-painting

# Install dependencies
npm install

# Start dev mode (hot reload)
npm run dev

# Build for production
npm run electron:build
```

---

## 📂 Project Structure

```
musical-painting/
├── electron/               # Electron main & preload
├── src/                    # React renderer (canvas + audio)
├── public/                 # Static assets (icons, etc.)
├── USER_GUIDE.md           # End-user documentation
├── DEVELOPER_GUIDE.md      # Developer documentation
├── package.json            # Scripts, deps, build config
└── ...
```

---

## 🧑‍💻 Contributing

Contributions are welcome! 🎉  
Ideas for improvement:
- Longer video recording options (5s / 30s)
- High-resolution PNG / WebM exports (e.g., 4K)
- Cross-platform builds (Windows/Linux)
- ML-driven visual styles

Please open an issue or PR if you’d like to help.

---

## 📜 License

MIT © 2025 [Your Name](https://github.com/your-username)

---
