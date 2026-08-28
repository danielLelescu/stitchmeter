# StitchMeter

**A low-tech, fully mechanical device for measuring suture-knot tightening force and knot-pull resistance**

*EPFL — Conception de mécanismes II · Groupe 25 · 2026*
*Lucas De Boi · Honoré Specq · Daniel Lelescu · Lilian Gardon · Titouan Beaux*
*Supervision: Dr Simon Henein*

---

## 🎥 Demo

<!-- Replace with a YouTube embed once the video is uploaded, e.g.:
<iframe width="560" height="315" src="https://www.youtube.com/embed/VIDEO_ID" title="StitchMeter demo" frameborder="0" allowfullscreen></iframe>
-->
[Watch the demo video](./assets/G25_Video1.mov)

---

## 🧵 Overview

StitchMeter is a **surgical training device** designed to measure two things surgeons care about when closing a wound with sutures:

1. **The force applied while tightening a knot** (Phase I)
2. **The force needed to pull a knot apart during a traction test** (Phase II)

The core design constraint was to eliminate **all friction** from the force-measurement chain. To achieve this, the entire measurement path is built from **flexure elements** (flexible blades, crossed-blade pivots, and buckling beams) rather than bearings, sliders, or electronics — making the device robust, calibration-free, and usable even in low-resource settings.

The device adapts to **three standard suture wire types** (EP2, EP6, EP9), each requiring a different stiffness range, via two independent mechanical stiffness-adjustment systems (a rotating-cam buckling mechanism for Phase I, and a tensioned-spring parallel-blade table for Phase II).

---

## ⚙️ How It Works

### Phase I — Knot tightening
As the user cinches the suture knot, one wound-edge block deflects a pair of parallel guiding blades. This deflection is amplified through a lever arm and read off a graduated scale — force is recovered directly from Hooke's law.

### Phase II — Knot-pull (traction) test
A separate mobile block applies tension to the knot through a second flexure spring (a stacked double parallel-blade "table"). A relative-displacement measurement between two blocks cancels out any knot relaxation during the pull, and a trailing needle captures the peak force reached.

### Stiffness adjustment
- **Phase I:** an asymmetric rotating cam selectively buckles 0, 1, or 2 preload blades, discretely lowering the guide stiffness for softer threads.
- **Phase II:** a vertical tension spring loads a double parallel-blade table; screwing a nut changes the preload and therefore the effective horizontal stiffness.

---

## 🏗️ Construction

- **Aluminum 7075 (Perunal-215)** — main monolithic housing and flexure blades (light, machinable, low-cost)
- **Böhler K190 tool steel** — cam, shaft, and AC spring (wear resistance at sliding interfaces)
- **Titanium 6Al-4V** — Phase II measurement needle pivot (best strength-to-stiffness ratio, maximizes angular travel)
- **Polycarbonate** — transparent enclosure panels, doubling as mechanical end-stops

Manufacturing combines 3-axis CNC milling (monolithic housing) with wire EDM and laser cutting (precision flexure blades), assembled flat on a surface plate to guarantee blade alignment.

All flexible elements are verified to survive **10⁵ cycles** with a safety factor ≥ 1.08, and the design has no non-conformities against the project specification.

---

## 📸 Gallery

<!-- Add rendered images/screenshots here, e.g.: -->
<!-- ![StitchMeter overview](./assets/overview.png) -->
<!-- ![Phase I mechanism](./assets/phase1.png) -->
<!-- ![Phase II mechanism](./assets/phase2.png) -->

---

## 📄 Documentation

| Document | Description |
|---|---|
| [Final presentation slides](./docs/G25_Slides.pdf) | Soutenance finale — design overview, results, discussion |
| [Detailed design report](./docs/G25_Rapport.pdf) | Full write-up: principles, dimensioning, stress analysis, material choices, BOM |
| [Design boards — Planche 1](./docs/G25_Planche1.pdf) | Concept board |
| [Design boards — Planche 2](./docs/G25_Planche2.pdf) | Concept board |
| [Design boards — Planche 3](./docs/G25_Planche3.pdf) | Concept board |
| [Design boards — Planche 4](./docs/G25_Planche4.pdf) | Concept board |
| [Design boards — Planche 5](./docs/G25_planche5.pdf) | Concept board |
| [CAD model (.step)](./cad/G25_Stitchmeter.step) | Full assembly, importable into any CAD software |

---

## ✅ Key Results

- **01** — The entire measurement chain relies on flexure elements: no friction between knot force and needle reading.
- **02** — A single device covers all three suture types (EP2 / EP6 / EP9) via discrete buckling (Phase I) and an adjustable spring (Phase II).
- **03** — Resolution stays within spec (ΔF ≤ 10% of reading) across the full range, for all three threads.
- **04** — Robust, low-tech, calibration-free, and field-usable — rated for 10⁵ cycles.

---

## 👥 Team

| Member | Contributions |
|---|---|
| Lucas De Boi | Final design board, Phase I amplification/guiding calculations, report sections 1–2.6 |
| Honoré Specq | Block C design, Phase II needle calculations, report sections 2.7–3.7 |
| Daniel Lelescu | Phase II needle calculations, Phase I discrete stiffness design, report sections 2.8.1–5 |
| Lilian Gardon | Phase I CAD modeling, discrete stiffness design and calculations |
| Titouan Beaux | Phase II CAD modeling, Block C design, Block B guiding calculations |

---

## 📜 License

*No license added yet — add one here if you'd like others to be able to reuse this work.*
