# 呪術廻戦 — JJK Cursed Technique
> A real-time hand-tracking web experience inspired by Jujutsu Kaisen.  
> Built by [@_whois._.adii](https://www.instagram.com/_whois._.adii) • [@aadi.devx](https://www.instagram.com/aadi.devx)

---

## What It Does

Open `jjk.html` in your browser and it activates your camera. The app tracks your hand gestures in real time and responds with animated cursed energy particle effects — each hand pose triggers a different JJK technique.

---

## Features

- Real-time hand tracking via MediaPipe Hands
- 4 unique cursed techniques triggered by gestures
- 20,000 particle system with Three.js + bloom post-processing
- Grain film overlay for cinematic feel
- Fully mobile-responsive (works on phones/tablets)
- Clickable watermarks linking to Instagram

---

## Techniques & Gestures

| Gesture | Technique | Effect |
|---|---|---|
| Index finger up only | **Red** — Reverse Cursed Technique | Red spiral arms, rotating fast |
| Index + Middle fingers up | **Void** — Infinite Void | Cyan ring + blue particle cloud |
| Pinch (index + thumb close) | **Purple** — Hollow Purple | Purple sphere + rotating chaos |
| All 4 fingers up | **Shrine** — Malevolent Shrine | Blood-red ground + pillars, upright lock |
| No gesture / hand down | **Neutral** | Dim blue ambient scatter |

---

## How to Use

**Desktop / Laptop**
1. Open `jjk.html` in Chrome or Edge (recommended)
2. Allow camera access when prompted
3. Hold your hand in front of the camera
4. Try the gestures in the table above

**Mobile**
1. Transfer `jjk.html` to your phone (AirDrop, Google Drive, cable, etc.)
2. Open in Chrome for Android or Safari for iOS
3. Tap "Allow" for camera access
4. Use your front camera — your hand appears mirrored naturally

> Works best in good lighting. Keep your hand clearly visible and within frame.

---

## Browser Compatibility

| Browser | Support |
|---|---|
| Chrome (desktop) | ✅ Full |
| Edge (desktop) | ✅ Full |
| Chrome (Android) | ✅ Full |
| Safari (iOS 16+) | ✅ Full |
| Firefox | ⚠️ Partial (WebGL works, camera may vary) |
| Samsung Internet | ⚠️ Partial |

> Camera and WebGL are both required. Private/incognito mode may block camera access.

---

## Tech Stack

| Library | Purpose |
|---|---|
| [Three.js r160](https://threejs.org/) | 3D particle rendering |
| [EffectComposer + UnrealBloomPass](https://threejs.org/docs/#examples/en/postprocessing/EffectComposer) | Bloom glow post-processing |
| [MediaPipe Hands](https://google.github.io/mediapipe/solutions/hands.html) | Real-time hand landmark detection |
| [MediaPipe Camera Utils](https://www.npmjs.com/package/@mediapipe/camera_utils) | Camera feed management |
| [MediaPipe Drawing Utils](https://www.npmjs.com/package/@mediapipe/drawing_utils) | Hand skeleton overlay |

All libraries are loaded via CDN — no install or build step needed.

---

## File Structure

```
jjk.html        ← The entire app (single self-contained file)
README.md       ← This file
```

Everything lives in one HTML file. No server, no dependencies to install, no build process.

---

## Performance Notes

- The particle system runs **20,000 points** — mid-range phones handle this fine
- Pixel ratio is capped at `2x` to avoid overloading high-DPI screens
- Hand model uses `modelComplexity: 1` (balanced accuracy vs speed)
- If it feels slow, open in Chrome and close other tabs

---

## Customisation

Want to tweak things? Here's what to look for inside `jjk.html`:

```javascript
const COUNT = 20000;          // Number of particles (lower = faster)
minDetectionConfidence: 0.7   // Hand detection sensitivity (0–1)
bloomPass.strength = 2.5      // Glow intensity per technique
```

Each technique has its own function (`getRed`, `getVoid`, `getPurple`, `getShrine`) — you can change colours, shapes, and spread by editing those.

---

## Credits

Made by  
**[@_whois._.adii](https://www.instagram.com/_whois._.adii)** — concept & design  
**[@aadi.devx](https://www.instagram.com/aadi.devx)** — development  

Inspired by the anime *Jujutsu Kaisen* by Gege Akutami / MAPPA.  
This is a fan project — not affiliated with or endorsed by the original creators.

---

## License

Personal / fan project. Free to use and share with credit.  
Please don't remove the watermarks if you redistribute.
