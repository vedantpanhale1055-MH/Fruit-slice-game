# ⚔️ Gesture Slice — Minimalist Edition

An interactive, browser-based motion game powered by **MediaPipe Hands** and **Vanilla JavaScript**. Slice fruits using high-precision hand tracking directly in your browser.

![Vanilla JS](https://img.shields.io/badge/Vanilla-JS-yellow)
![MediaPipe](https://img.shields.io/badge/AI-MediaPipe-blue)
![Status](https://img.shields.io/badge/Status-Active-brightgreen)

---

## ✨ Features
* 🚀 **Zero Latency Tracking**: Optimized for 1:1 movement accuracy.
* ✋ **Minimalist HUD**: High-contrast UI featuring a "Start Engine" initialization sequence.
* 🍎 **Physics-Based Dynamics**: Fruits feature randomized jump heights and constant gravity.
* 💣 **Avoid Bombs**: Tactical gameplay requires precise movement to avoid score penalties.

---

## ⚙️ How It Works (Technical Logic)

The core engine synchronizes a computer vision pipeline with a 2D physics loop. 
### 1. Computer Vision Pipeline
The app utilizes the `@mediapipe/hands` solution to identify 21 hand landmarks.
* **Targeting**: The game tracks **Landmark 8** (Index Finger Tip).
* **Coordinate Mapping**: Normalized coordinates are mapped to the browser's `window.innerWidth`.
* **Mirroring**: The x-axis is inverted (`1 - landmark.x`) for a natural "mirror" feel.

### 2. Physics & Collision Logic
* **Kinematics**: Fruits reach their apex using $V_y = -\sqrt{2 \cdot g \cdot h}$.
* **Slice Logic**: The game checks the shortest distance from the fruit center to the line segment formed by your finger's position between two frames. If $dist < \text{radius}$, a slice is registered.

---

## 🎮 Local Setup
1. Open `Cutfruit.html` via **Live Server**.
2. Enable your webcam and wait for **✅ Tracking Active**.
3. **Clone the repository**:
   ```bash
   git clone [https://github.com/vedantpanhale1055-MH/Fruit-slice-game.git](https://github.com/vedantpanhale1055-MH/Fruit-slice-game.git)
   
---
Developed by **Vedant Panhale** 
