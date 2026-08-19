# Polarity

**A one-tap, endless reflex game. Match your color. Don't stop.**

![Platform](https://img.shields.io/badge/platform-Android%20%7C%20Web-black)
![Made with](https://img.shields.io/badge/made%20with-HTML5%20Canvas-black)
![Status](https://img.shields.io/badge/status-MVP-black)

---

## About

Polarity is a minimalist, endless reflex game built around a single rule: **tap to flip your color, and match the wall's color to pass through.** There's no second mechanic to learn — just an ever-tightening test of timing as the walls speed up and new patterns get thrown at you.

The whole game runs on one input (tap / spacebar), rendered on a single HTML5 canvas with no external game engine — just vanilla JS, tuned difficulty curves, and a dark, distraction-free UI where color is reserved entirely for gameplay.

**Built by Lochan.**

---

## How to Play

1. Tap anywhere to start.
2. Your dot has two states — **ember** (warm) and **ion** (cool).
3. Walls scroll toward you in one of those two colors.
4. Tap to flip your color and match the wall before it reaches you.
5. Miss, and it's over. Your best score is saved on-device.

Difficulty escalates the longer you survive: walls close in faster, and new patterns (paired walls, rapid triples) get introduced at score milestones — so the challenge keeps evolving instead of just getting faster.

---

## Two Versions

This repo ships two ready-to-run builds of the same game:

### 🌐 Web / PWA — [`/pwa`](./pwa)
A installable Progressive Web App. Works in any modern browser, installs to an Android home screen like a native app, and works offline via a service worker.

```
cd pwa
# serve locally, e.g.:
npx serve .
```
Or just open `pwa/index.html` directly in a browser to play instantly — no build step required.

### 🤖 Android (Capacitor) — [`/android-studio`](./android-studio)
A native Android project wrapping the same game in a WebView shell via [Capacitor](https://capacitorjs.com), ready to build a signed APK in Android Studio.

```
cd android-studio
npm install
npx cap add android      # first time only
npx cap sync android
npx cap open android
```
Then in Android Studio: **Build → Generate Signed Bundle / APK → APK**.

---

## Features

- Single-input controls — tap or spacebar, nothing else to learn
- Procedural, escalating difficulty (speed, spawn rate, and pattern variety all scale with score)
- Persistent high score via `localStorage`
- Dark, minimal UI — color appears only on gameplay elements, never the chrome
- Installable as a PWA or buildable as a native Android APK from the same codebase
- Zero external game engine — plain HTML5 Canvas + JavaScript

---

## Tech Stack

| Layer | Tech |
|---|---|
| Rendering | HTML5 Canvas (2D context) |
| Logic | Vanilla JavaScript |
| Styling | CSS (custom properties, no framework) |
| Persistence | `localStorage` |
| Native wrapper | [Capacitor](https://capacitorjs.com) |
| Offline support | Service Worker + Web App Manifest |

---

## Project Structure

```
polarity/
├── pwa/                  # Web / installable PWA version
│   ├── index.html
│   ├── manifest.json
│   ├── sw.js
│   ├── icon-192.png
│   └── icon-512.png
├── android-studio/        # Capacitor project for native Android builds
│   ├── www/                # game assets (same as /pwa)
│   ├── package.json
│   ├── capacitor.config.json
│   └── README.md            # Android-specific build steps
└── README.md               # you are here
```

---

## License

Feel free to fork, learn from, or build on this project. Attribution appreciated.
