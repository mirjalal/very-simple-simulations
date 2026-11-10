# Very Simple Simulations ⚡🧪

> **Deep, deterministic, zero-dependency in-browser physics laboratories and engineering simulators.**

[![GitHub Pages](https://img.shields.io/badge/Live%20Demos-GitHub%20Pages-2ea44f?style=for-the-badge&logo=github)](https://mirjalal.github.io/very-simple-simulations/)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg?style=for-the-badge)](LICENSE)
[![Zero Dependencies](https://img.shields.io/badge/Dependencies-Zero%20(Pure%20Vanilla%20JS)-orange?style=for-the-badge)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![60 FPS Canvas](https://img.shields.io/badge/Renderer-HTML5%20Canvas%202D-violet?style=for-the-badge)](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API)
[![Web Audio API](https://img.shields.io/badge/Sound-Web%20Audio%20Synthesis-cyan?style=for-the-badge)](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API)

---

## 🌟 Overview

Despite the name, **Very Simple Simulations** is a collection of high-fidelity, interactive physics and engineering labs that run **entirely in your web browser with zero build tools, zero dependencies, and zero installations**. 

Each simulator is packaged as a **single, standalone HTML file** combining:
- **Real-time 60 FPS physics engines** using symplectic Euler and numerical integration.
- **Interactive telemetry HUDs** displaying real-time G-forces, slip angles, torque curves, and aerodynamic vector decompositions.
- **Procedural sound synthesis** using the HTML5 Web Audio API (procedural diesel engine harmonics, pneumatic air brake purges, aerodynamic airflow).
- **Modern responsive engineering interfaces** built with Tailwind CSS and `JetBrains Mono` typography.

---

## 🚀 Live Simulations

| Simulation | Domain | Core Concepts | Live Demo |
| :--- | :--- | :--- | :--- |
| **🏎️ APEX LAB** | Motorsports Dynamics | Trail Braking, Traction Ellipse, Weight Transfer, Apex Geometries | [Launch Lab ↗](https://mirjalal.github.io/very-simple-simulations/apex_trail_braking_telemetry_trainer.html) |
| **🚛 RIG LAB** | Drivetrain & Soil Mechanics | Torque Multiplication, Tandem Axles, Soil Rut Excavation, Diff Lock | [Launch Lab ↗](https://mirjalal.github.io/very-simple-simulations/heavy_rig_drivetrain_terrain_physics_lab.html) |
| **🪁 AeroKite** | Tethered Aerodynamics | Lift & Drag Vectors, Apparent Wind, Tether Catenary, Stall Dynamics | [Launch Lab ↗](https://mirjalal.github.io/very-simple-simulations/kite_physics_aerodynamics_simulation.html) |

---

## 🧪 Detailed Laboratory Breakdown

### 1. 🏎️ APEX LAB: Motorsports Telemetry & Pedal Modulation Sim
*File:* [`apex_trail_braking_telemetry_trainer.html`](apex_trail_braking_telemetry_trainer.html)

A high-performance vehicle dynamics simulator designed to teach **trail braking** and **racing line optimization**. Compare your braking threshold and throttle release curves against an ideal AI telemetry ghost in real time.

#### Key Engineering Features:
- **Friction Circle / Traction Ellipse**: Models tire adhesion limit ($F_{x}^2 / F_{x,\max}^2 + F_{y}^2 / F_{y,\max}^2 \le 1$). Braking while turning splits the traction budget.
- **Dynamic Weight Transfer**: Pitch and roll calculations shift normal loads between front and rear axles, dynamically adjusting available steering authority and lockup thresholds.
- **Apex Philosophy Comparison**:
  - **Late Apex**: Prioritizes early throttle commitment for maximum exit speed onto following straights.
  - **Geometric Apex**: Balances entry and exit radius for maximum mid-corner apex speed.
  - **Early Apex**: Defensive racing line trading exit velocity for aggressive corner entry.
- **Live Telemetry Acquisition**: Real-time strip charts for speed ($v$), longitudinal acceleration ($G_x$), lateral acceleration ($G_y$), throttle position, brake pressure, and delta timing ($\Delta t$).
- **Circuit Geometries**: Presets for 45°, 90°, 135°, and 180° hairpins, plus constant, decreasing radius, increasing radius, and double apex corners.

#### Controls:
| Input | Action |
| :--- | :--- |
| `W` / `↑` / `Shift` | Throttle / Gas Pedal (Progressive modulation) |
| `S` / `↓` | Brake Pedal (Threshold & Trail Braking) |
| `A` / `D` or `←` / `→` | Steering (Manual mode) |
| `R` / `Space` | Reset telemetry and retry run |
| UI Toggles | Auto-Steer / Pedals-Only Mode, AI Ghost, Apex Guides |

---

### 2. 🚛 RIG LAB: Heavy-Duty Semi & B-Double Drivetrain Simulator
*File:* [`heavy_rig_drivetrain_terrain_physics_lab.html`](heavy_rig_drivetrain_terrain_physics_lab.html)

A detailed longitudinal vehicle dynamics and terrain mechanics simulator modeling multi-axle commercial transport vehicles on challenging topographies.

#### Key Engineering Features:
- **Powertrain Simulation**:
  - Realistic diesel engine torque curves (540 HP – 750 HP, 2600–3550 Nm torque @ 1000–1400 RPM).
  - Multi-speed heavy haul transmissions (Range & Splitter 12/16/18-speed manual and AMT automated manual).
  - Driveline torque multiplication: $T_{\text{wheel}} = T_{\text{engine}} \times R_{\text{gear}} \times R_{\text{final}} \times \eta_{\text{driveline}}$.
- **Terramechanics & Rut Excavation**:
  - Wheel slip ratio: $s = \frac{\omega r - v}{\max(\omega r, v)}$.
  - High wheel slip on soft surfaces (Mud, Loose Sand, Snow) cuts into the subgrade, digging deep ruts.
  - **Frame Bottoming & Immobilization**: Once ruts exceed axle ground clearance, frame rails high-center on the mud pack and bulldozing resistance halts the rig.
- **Traction & Drivetrain Controls**:
  - Open differential vs. 100% Spool Cross-Axle **Differential Lock** (`[L]`).
  - 6x4 Tandem Drive vs. 6x6 All-Wheel-Drive engagement.
  - Multi-stage hydrodynamic driveline retarder / Jake brake (`[Space]` / `[V]`).
  - Pneumatic service brakes with simulated reservoir pressure depletion and pneumatic purge sound effects.
- **Audio Synthesizer Engine**: Procedural Web Audio engine generating realistic low-frequency diesel engine rumble, turbo spool whistle, gear whine, and air brake discharge pops.

#### Controls:
| Input | Action |
| :--- | :--- |
| `W` / `↑` | Accelerator / Diesel Throttle |
| `S` / `↓` | Pneumatic Service Brake |
| `Q` / `E` | Sequential Downshift / Upshift (Manual Mode) |
| `L` | Toggle Differential Lock (Open vs Spool Lock) |
| `Space` / `V` | Cycle Multi-Stage Hydrodynamic Retarder / Jake Brake |
| `B` | Emergency Spring Parking Brake |
| `R` | Restart Session & Unbog Rig |

---

### 3. 🪁 AeroKite: Tethered Aerodynamics & Force Vector Lab
*File:* [`kite_physics_aerodynamics_simulation.html`](kite_physics_aerodynamics_simulation.html)

A physical simulation of a tethered flexible wing in an atmospheric boundary layer wind field with real-time vector HUD analysis.

#### Key Engineering Features:
- **Aerodynamic Vector Decomposition**:
  - Lift: $F_L = \frac{1}{2} \rho v_{\text{app}}^2 S C_L$
  - Drag: $F_D = \frac{1}{2} \rho v_{\text{app}}^2 S C_D$
  - Equilibrium Tether Tension: $\vec{F}_T = -(\vec{F}_L + \vec{F}_D + \vec{F}_g)$
  - Theoretical Steady Flight Angle: $\theta = \arctan\left(\frac{F_L - F_g}{F_D}\right)$
- **Atmospheric Wind Shear**: Models the planetary boundary layer velocity profile with altitude: $v(z) = v_0 \left(\frac{z}{z_0}\right)^\alpha$.
- **Dynamic Gusts & Apparent Wind Surge**: Winch tugs pull the kite downwind/upwind, modifying relative apparent wind speed and inducing rapid lift spikes.
- **Flight Envelope**: Models angle of attack ($\alpha$), stall inception, bridle geometry, tether catenary sag, and aspect ratio variations.
- **HUD Modes**: Free-Body Diagram (FBD) force vector arrows, streamline wind-tunnel visualization, telemetry monitors, and altimeter.

#### Controls:
| Input | Action |
| :--- | :--- |
| `Space` (Hold) | Winch Tug / Rapid Line Pull (spikes apparent wind & lift) |
| Sliders | Wind Speed, Bridle Angle ($\alpha$), Line Length ($L$), Mass, Wing Area |
| Presets | Standard Diamond, Ultralight Breeze, Storm Gale, High-AoA Stall, 300m Altitude |
| Buttons | Vector Overlay, Free Body Diagram HUD, Streamlines, Pause / Step |

---

## 🛠️ Architecture & Design Principles

```
very-simple-simulations/
├── index.html                                  # Central interactive launcher & showcase hub
├── apex_trail_braking_telemetry_trainer.html   # Standalone Motorsports Dynamics Lab
├── heavy_rig_drivetrain_terrain_physics_lab.html # Standalone Heavy Drivetrain Lab
├── kite_physics_aerodynamics_simulation.html   # Standalone Tethered Aerodynamics Lab
└── README.md                                   # Documentation & reference manual
```

1. **Zero Build Step**: No `npm install`, no Webpack, no Vite, no node_modules. Clone and run immediately.
2. **Deterministic Physics**: Real-time Euler integration executed within `requestAnimationFrame` render loops.
3. **Pure Web Standards**: HTML5 Canvas 2D, Web Audio API, Vanilla ES6+ JavaScript, Tailwind CSS CDN.
4. **Self-Contained**: Each simulation can be saved and run offline as a single HTML file without an internet connection (Google Fonts fallback gracefully).

---

## 💻 Running Locally

### Option 1: Direct File Opening (No Web Server Needed)
Simply double-click `index.html` or any simulation `.html` file, or open it in your favorite browser:
```bash
# macOS
open index.html

# Linux
xdg-open index.html

# Windows
start index.html
```

### Option 2: Lightweight HTTP Server
If you want to run a local dev server:
```bash
# Using Python 3
python3 -m http.server 8080

# Using Node (npx)
npx serve .
```
Then visit `http://localhost:8080` in your browser.

---

## 🗺️ Roadmap & Planned Simulations

- [ ] **Orbital Mechanics & Hohmann Transfer Lab**: 2-body and 3-body gravitational slingshot trajectory simulator.
- [ ] **Sailing Aerodynamics & Polar Plots**: Upwind sailing physics, keel hydrodynamic leeway, and true vs. apparent wind vectors.
- [ ] **Coupled Pendulum Waves & Resonance**: Dynamic vibration absorbers and energy exchange visualization.
- [ ] **Quadcopter Drone PID Flight Controller**: Interactive P/I/D gain tuning for pitch, roll, and altitude hover stabilization.

---

## 🤝 Contributing

Contributions, simulations, ideas, and bug fixes are welcome!
1. Fork the repository.
2. Create your simulation in a self-contained `.html` file.
3. Follow the zero-dependency, standalone architecture.
4. Submit a Pull Request.

---

## 📄 License

This project is licensed under the **MIT License** — feel free to use, modify, learn from, and share these simulations for educational, academic, or personal projects.
