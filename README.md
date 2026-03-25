# 🎵 Pitch Shifter

A lightweight **Progressive Web App** that records your voice and lets you shift its pitch up or down — without changing the speed of playback.

Designed to help communicate with elderly people who may have difficulty hearing certain frequency ranges.

---

## ✨ Features

- 🎙️ **Record** your voice directly in the browser
- 🎚️ **Shift pitch** from −12 to +12 semitones with a single slider
- ⏱️ **Preserves duration** — pitch changes, speed stays the same
- 📱 **Installable PWA** — works offline, can be added to the home screen on iOS & Android
- 🔒 **100% client-side** — no server, no data ever leaves your device

---

## 🚀 Live App

👉 **[Open Pitch Shifter](https://YOUR-USERNAME.github.io/pitch-shifter/)**

> Replace `YOUR-USERNAME` with your GitHub username after deploying.

---

## 📲 How to Install on Phone

**Android (Chrome):**
1. Open the live link above in Chrome
2. Tap the three-dot menu → *Add to Home Screen*

**iOS (Safari):**
1. Open the live link above in Safari
2. Tap the Share button → *Add to Home Screen*

---

## 🛠️ Deploy to GitHub Pages (step by step)

### Option A — Upload via GitHub web interface

1. Go to [github.com](https://github.com) and **create a new repository** (e.g. `pitch-shifter`). Set it to **Public**.
2. Click **Add file → Upload files**.
3. Drag and drop **all files** from this folder:
   ```
   index.html
   manifest.json
   sw.js
   icon-192.png
   icon-512.png
   .nojekyll
   README.md
   ```
4. Click **Commit changes**.
5. Go to **Settings → Pages**.
6. Under *Source*, select **Deploy from a branch** → branch `main` → folder `/ (root)`.
7. Click **Save**. Your app will be live at `https://YOUR-USERNAME.github.io/pitch-shifter/` within a minute.

### Option B — Git command line

```bash
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/pitch-shifter.git
git push -u origin main
```

Then enable Pages in **Settings → Pages** as described in step 5–7 above.

---

## 🔬 How it works

Pitch shifting is achieved entirely with the **Web Audio API**:

1. The recording is decoded into an `AudioBuffer`.
2. An `OfflineAudioContext` is created with a **resampled sample rate** (`originalSR × pitchRatio`).
3. The buffer is rendered into this context — the browser fits the same samples into a different timebase.
4. The rendered data is copied into a new `AudioBuffer` stamped with the **playback context's real sample rate**.
5. The browser reinterprets the samples at the new rate → **pitch shifts by the ratio, duration stays identical** ✓

No external libraries. No server. Pure Web Audio.

---

## ⚠️ Disclaimer

This is not a medical device, requires trial and error to find a proper pitch, and does not substitute acoustic devices.

---

## 👤 Author

Developed by **Daniele Proverbio**, 2026.

---

## 📄 License

MIT — free to use, modify, and distribute.
