#!/bin/bash

# ============================================================
# Q-FIND README Setup Script
# Run this from your repo root:
#   bash setup_readme.sh
# ============================================================

set -e

echo "🚀 Setting up README assets..."

# Create assets directory
mkdir -p assets

# ============================================================
# 1. BANNER SVG
# ============================================================
cat > assets/banner.svg << 'BANNEREOF'
<svg width="900" height="200" viewBox="0 0 900 200" xmlns="http://www.w3.org/2000/svg">
  <defs>
    <linearGradient id="bg" x1="0%" y1="0%" x2="100%" y2="100%">
      <stop offset="0%" style="stop-color:#07070f"/>
      <stop offset="50%" style="stop-color:#0d1117"/>
      <stop offset="100%" style="stop-color:#07070f"/>
    </linearGradient>
    <linearGradient id="title-grad" x1="0%" y1="0%" x2="100%" y2="0%">
      <stop offset="0%" style="stop-color:#00f5d4"/>
      <stop offset="100%" style="stop-color:#4cc9f0"/>
    </linearGradient>
    <filter id="glow">
      <feGaussianBlur stdDeviation="3" result="coloredBlur"/>
      <feMerge><feMergeNode in="coloredBlur"/><feMergeNode in="SourceGraphic"/></feMerge>
    </filter>
    <filter id="softglow">
      <feGaussianBlur stdDeviation="8" result="coloredBlur"/>
      <feMerge><feMergeNode in="coloredBlur"/><feMergeNode in="SourceGraphic"/></feMerge>
    </filter>
  </defs>
  <rect width="900" height="200" fill="url(#bg)" rx="12"/>
  <g opacity="0.06" stroke="#00f5d4" stroke-width="0.5">
    <line x1="0" y1="40" x2="900" y2="40"/>
    <line x1="0" y1="80" x2="900" y2="80"/>
    <line x1="0" y1="120" x2="900" y2="120"/>
    <line x1="0" y1="160" x2="900" y2="160"/>
    <line x1="150" y1="0" x2="150" y2="200"/>
    <line x1="300" y1="0" x2="300" y2="200"/>
    <line x1="450" y1="0" x2="450" y2="200"/>
    <line x1="600" y1="0" x2="600" y2="200"/>
    <line x1="750" y1="0" x2="750" y2="200"/>
  </g>
  <g transform="translate(110, 100)" filter="url(#softglow)">
    <circle cx="0" cy="0" r="85" fill="none" stroke="#00f5d4" stroke-width="0.5" opacity="0.15"/>
    <circle cx="0" cy="0" r="72" fill="none" stroke="#00f5d4" stroke-width="0.6" opacity="0.2"/>
    <circle cx="0" cy="0" r="60" fill="none" stroke="#00f5d4" stroke-width="0.8" opacity="0.3"/>
    <circle cx="0" cy="0" r="48" fill="none" stroke="#00f5d4" stroke-width="1" opacity="0.4"/>
    <circle cx="0" cy="0" r="37" fill="none" stroke="#00f5d4" stroke-width="1.2" opacity="0.5"/>
    <circle cx="0" cy="0" r="27" fill="none" stroke="#4cc9f0" stroke-width="1.4" opacity="0.6"/>
    <circle cx="0" cy="0" r="18" fill="none" stroke="#4cc9f0" stroke-width="1.6" opacity="0.7"/>
    <circle cx="0" cy="0" r="11" fill="none" stroke="#4cc9f0" stroke-width="1.8" opacity="0.85"/>
    <circle cx="0" cy="0" r="5.5" fill="none" stroke="#00f5d4" stroke-width="2" opacity="1" filter="url(#glow)"/>
    <circle cx="0" cy="0" r="3" fill="none" stroke="#ffd60a" stroke-width="1.5" stroke-dasharray="2,2" opacity="0.9" filter="url(#glow)"/>
    <circle cx="0" cy="0" r="1.5" fill="#ffd60a" opacity="1"/>
  </g>
  <ellipse cx="110" cy="100" rx="90" ry="90" fill="#00f5d4" opacity="0.03"/>
  <text x="230" y="72" font-family="'Courier New', monospace" font-size="11" fill="#00f5d4" opacity="0.7" letter-spacing="4">FLOATING-POINT VISUALIZATION</text>
  <text x="228" y="115" font-family="Georgia, serif" font-size="28" font-weight="bold" fill="url(#title-grad)" filter="url(#glow)">Iterated Root Convergence</text>
  <text x="230" y="142" font-family="'Courier New', monospace" font-size="12" fill="rgba(255,255,255,0.45)" letter-spacing="1">N^(1/n) → 1  ·  Making the invisible visible</text>
  <g transform="translate(230, 168)">
    <rect x="0" y="-14" width="80" height="20" rx="4" fill="#00f5d410" stroke="#00f5d444" stroke-width="1"/>
    <text x="8" y="0" font-family="'Courier New', monospace" font-size="10" fill="#00f5d4">📦 Zenodo v3</text>
    <rect x="90" y="-14" width="64" height="20" rx="4" fill="#ffd60a10" stroke="#ffd60a44" stroke-width="1"/>
    <text x="98" y="0" font-family="'Courier New', monospace" font-size="10" fill="#ffd60a">⚖ MIT</text>
    <rect x="164" y="-14" width="90" height="20" rx="4" fill="#4cc9f010" stroke="#4cc9f044" stroke-width="1"/>
    <text x="172" y="0" font-family="'Courier New', monospace" font-size="10" fill="#4cc9f0">🌐 OpenAIRE</text>
    <rect x="264" y="-14" width="110" height="20" rx="4" fill="#f7258510" stroke="#f7258544" stroke-width="1"/>
    <text x="272" y="0" font-family="'Courier New', monospace" font-size="10" fill="#f72585">📈 92% comprehension</text>
  </g>
  <text x="810" y="45" font-family="Georgia, serif" font-size="13" fill="#00f5d4" opacity="0.6" text-anchor="middle">lim N^(1/n) = 1</text>
  <text x="810" y="62" font-family="'Courier New', monospace" font-size="9" fill="rgba(255,255,255,0.2)" text-anchor="middle">n → ∞</text>
  <circle cx="16" cy="16" r="3" fill="#00f5d4" opacity="0.4"/>
  <circle cx="884" cy="16" r="3" fill="#00f5d4" opacity="0.4"/>
  <circle cx="16" cy="184" r="3" fill="#00f5d4" opacity="0.4"/>
  <circle cx="884" cy="184" r="3" fill="#00f5d4" opacity="0.4"/>
  <rect width="900" height="200" fill="none" stroke="#00f5d4" stroke-width="1" opacity="0.15" rx="12"/>
</svg>
BANNEREOF

echo "✅ banner.svg created"

# ============================================================
# 2. CONVERGENCE VISUALIZATION SVG
# ============================================================
cat > assets/convergence-viz.svg << 'CVIZEOF'
<svg width="900" height="320" viewBox="0 0 900 320" xmlns="http://www.w3.org/2000/svg">
  <defs>
    <linearGradient id="bg2" x1="0%" y1="0%" x2="100%" y2="100%">
      <stop offset="0%" style="stop-color:#0d1117"/>
      <stop offset="100%" style="stop-color:#07070f"/>
    </linearGradient>
    <filter id="glow2">
      <feGaussianBlur stdDeviation="2.5" result="coloredBlur"/>
      <feMerge><feMergeNode in="coloredBlur"/><feMergeNode in="SourceGraphic"/></feMerge>
    </filter>
  </defs>
  <rect width="900" height="320" fill="url(#bg2)" rx="12"/>
  <rect width="900" height="320" fill="none" stroke="#ffffff10" stroke-width="1" rx="12"/>
  <text x="450" y="36" font-family="'Courier New', monospace" font-size="13" fill="#ffffff60" text-anchor="middle" letter-spacing="3">FOUR CONVERGENCE FAMILIES · ADAPTIVE SCALING</text>
  <rect x="20" y="55" width="195" height="220" rx="8" fill="#00f5d408" stroke="#00f5d430" stroke-width="1"/>
  <rect x="235" y="55" width="195" height="220" rx="8" fill="#4cc9f008" stroke="#4cc9f030" stroke-width="1"/>
  <rect x="450" y="55" width="195" height="220" rx="8" fill="#ffd60a08" stroke="#ffd60a30" stroke-width="1"/>
  <rect x="665" y="55" width="215" height="220" rx="8" fill="#f7258508" stroke="#f7258530" stroke-width="1"/>
  <text x="117" y="78" font-family="'Courier New', monospace" font-size="10" fill="#00f5d4" text-anchor="middle" letter-spacing="1">ALGEBRAIC · 1/n</text>
  <text x="332" y="78" font-family="'Courier New', monospace" font-size="10" fill="#4cc9f0" text-anchor="middle" letter-spacing="1">LOGARITHMIC · ln(n)/n</text>
  <text x="547" y="78" font-family="'Courier New', monospace" font-size="10" fill="#ffd60a" text-anchor="middle" letter-spacing="1">EXPONENTIAL · e⁻ⁿ</text>
  <text x="772" y="78" font-family="'Courier New', monospace" font-size="10" fill="#f72585" text-anchor="middle" letter-spacing="1">DOUBLY SLOW · 1/(n ln n)</text>
  <g transform="translate(117,170)" filter="url(#glow2)">
    <circle cx="0" cy="0" r="88" fill="none" stroke="#00f5d4" stroke-width="0.4" opacity="0.1"/>
    <circle cx="0" cy="0" r="79" fill="none" stroke="#00f5d4" stroke-width="0.5" opacity="0.15"/>
    <circle cx="0" cy="0" r="70" fill="none" stroke="#00f5d4" stroke-width="0.6" opacity="0.2"/>
    <circle cx="0" cy="0" r="62" fill="none" stroke="#00f5d4" stroke-width="0.7" opacity="0.25"/>
    <circle cx="0" cy="0" r="54" fill="none" stroke="#00f5d4" stroke-width="0.8" opacity="0.3"/>
    <circle cx="0" cy="0" r="47" fill="none" stroke="#00f5d4" stroke-width="0.9" opacity="0.38"/>
    <circle cx="0" cy="0" r="40" fill="none" stroke="#00f5d4" stroke-width="1" opacity="0.46"/>
    <circle cx="0" cy="0" r="34" fill="none" stroke="#00f5d4" stroke-width="1.1" opacity="0.54"/>
    <circle cx="0" cy="0" r="28" fill="none" stroke="#00f5d4" stroke-width="1.2" opacity="0.62"/>
    <circle cx="0" cy="0" r="22" fill="none" stroke="#00f5d4" stroke-width="1.3" opacity="0.7"/>
    <circle cx="0" cy="0" r="17" fill="none" stroke="#00f5d4" stroke-width="1.4" opacity="0.78"/>
    <circle cx="0" cy="0" r="12" fill="none" stroke="#00f5d4" stroke-width="1.5" opacity="0.86"/>
    <circle cx="0" cy="0" r="8" fill="none" stroke="#00f5d4" stroke-width="1.6" opacity="0.93"/>
    <circle cx="0" cy="0" r="4.5" fill="none" stroke="#00f5d4" stroke-width="1.8" opacity="1"/>
    <circle cx="0" cy="0" r="2" fill="none" stroke="#ffd60a" stroke-width="1.2" stroke-dasharray="2,1.5" opacity="0.9"/>
    <circle cx="0" cy="0" r="0.8" fill="#ffd60a"/>
    <text x="0" y="105" font-family="'Courier New', monospace" font-size="9" fill="#00f5d490" text-anchor="middle">n=1 → n=40</text>
    <text x="0" y="118" font-family="'Courier New', monospace" font-size="8" fill="#ffffff40" text-anchor="middle">SEVERE artifacts</text>
  </g>
  <g transform="translate(332,170)" filter="url(#glow2)">
    <circle cx="0" cy="0" r="88" fill="none" stroke="#4cc9f0" stroke-width="0.4" opacity="0.1"/>
    <circle cx="0" cy="0" r="80" fill="none" stroke="#4cc9f0" stroke-width="0.45" opacity="0.15"/>
    <circle cx="0" cy="0" r="72" fill="none" stroke="#4cc9f0" stroke-width="0.5" opacity="0.2"/>
    <circle cx="0" cy="0" r="64" fill="none" stroke="#4cc9f0" stroke-width="0.6" opacity="0.26"/>
    <circle cx="0" cy="0" r="57" fill="none" stroke="#4cc9f0" stroke-width="0.7" opacity="0.32"/>
    <circle cx="0" cy="0" r="50" fill="none" stroke="#4cc9f0" stroke-width="0.8" opacity="0.39"/>
    <circle cx="0" cy="0" r="43" fill="none" stroke="#4cc9f0" stroke-width="0.9" opacity="0.46"/>
    <circle cx="0" cy="0" r="37" fill="none" stroke="#4cc9f0" stroke-width="1" opacity="0.53"/>
    <circle cx="0" cy="0" r="31" fill="none" stroke="#4cc9f0" stroke-width="1.1" opacity="0.61"/>
    <circle cx="0" cy="0" r="25" fill="none" stroke="#4cc9f0" stroke-width="1.2" opacity="0.69"/>
    <circle cx="0" cy="0" r="19" fill="none" stroke="#4cc9f0" stroke-width="1.4" opacity="0.77"/>
    <circle cx="0" cy="0" r="13" fill="none" stroke="#4cc9f0" stroke-width="1.6" opacity="0.86"/>
    <circle cx="0" cy="0" r="7" fill="none" stroke="#4cc9f0" stroke-width="1.8" opacity="0.94"/>
    <circle cx="0" cy="0" r="2" fill="none" stroke="#ffd60a" stroke-width="1.2" stroke-dasharray="2,1.5" opacity="0.9"/>
    <circle cx="0" cy="0" r="0.8" fill="#ffd60a"/>
    <text x="0" y="105" font-family="'Courier New', monospace" font-size="9" fill="#4cc9f090" text-anchor="middle">n=1 → n=40</text>
    <text x="0" y="118" font-family="'Courier New', monospace" font-size="8" fill="#ffffff40" text-anchor="middle">MOST severe artifacts</text>
  </g>
  <g transform="translate(547,170)" filter="url(#glow2)">
    <circle cx="0" cy="0" r="88" fill="none" stroke="#ffd60a" stroke-width="0.5" opacity="0.12"/>
    <circle cx="0" cy="0" r="60" fill="none" stroke="#ffd60a" stroke-width="0.8" opacity="0.2"/>
    <circle cx="0" cy="0" r="35" fill="none" stroke="#ffd60a" stroke-width="1.2" opacity="0.35"/>
    <circle cx="0" cy="0" r="18" fill="none" stroke="#ffd60a" stroke-width="1.6" opacity="0.55"/>
    <circle cx="0" cy="0" r="8" fill="none" stroke="#ffd60a" stroke-width="2" opacity="0.75"/>
    <circle cx="0" cy="0" r="3.5" fill="none" stroke="#ffd60a" stroke-width="2.2" opacity="0.95"/>
    <circle cx="0" cy="0" r="2" fill="none" stroke="#ffd60a" stroke-width="1.2" stroke-dasharray="2,1.5" opacity="0.9"/>
    <circle cx="0" cy="0" r="0.8" fill="#ffd60a"/>
    <text x="0" y="105" font-family="'Courier New', monospace" font-size="9" fill="#ffd60a90" text-anchor="middle">n=1 → n=40</text>
    <text x="0" y="118" font-family="'Courier New', monospace" font-size="8" fill="#ffffff40" text-anchor="middle">MINIMAL artifacts</text>
  </g>
  <g transform="translate(772,170)" filter="url(#glow2)">
    <circle cx="0" cy="0" r="88" fill="none" stroke="#f72585" stroke-width="0.35" opacity="0.1"/>
    <circle cx="0" cy="0" r="84" fill="none" stroke="#f72585" stroke-width="0.38" opacity="0.13"/>
    <circle cx="0" cy="0" r="80" fill="none" stroke="#f72585" stroke-width="0.41" opacity="0.16"/>
    <circle cx="0" cy="0" r="76" fill="none" stroke="#f72585" stroke-width="0.44" opacity="0.19"/>
    <circle cx="0" cy="0" r="72" fill="none" stroke="#f72585" stroke-width="0.47" opacity="0.22"/>
    <circle cx="0" cy="0" r="68" fill="none" stroke="#f72585" stroke-width="0.5" opacity="0.26"/>
    <circle cx="0" cy="0" r="63" fill="none" stroke="#f72585" stroke-width="0.55" opacity="0.31"/>
    <circle cx="0" cy="0" r="58" fill="none" stroke="#f72585" stroke-width="0.6" opacity="0.36"/>
    <circle cx="0" cy="0" r="53" fill="none" stroke="#f72585" stroke-width="0.65" opacity="0.41"/>
    <circle cx="0" cy="0" r="48" fill="none" stroke="#f72585" stroke-width="0.7" opacity="0.47"/>
    <circle cx="0" cy="0" r="43" fill="none" stroke="#f72585" stroke-width="0.8" opacity="0.53"/>
    <circle cx="0" cy="0" r="38" fill="none" stroke="#f72585" stroke-width="0.9" opacity="0.59"/>
    <circle cx="0" cy="0" r="33" fill="none" stroke="#f72585" stroke-width="1" opacity="0.65"/>
    <circle cx="0" cy="0" r="28" fill="none" stroke="#f72585" stroke-width="1.1" opacity="0.72"/>
    <circle cx="0" cy="0" r="23" fill="none" stroke="#f72585" stroke-width="1.2" opacity="0.79"/>
    <circle cx="0" cy="0" r="18" fill="none" stroke="#f72585" stroke-width="1.4" opacity="0.85"/>
    <circle cx="0" cy="0" r="13" fill="none" stroke="#f72585" stroke-width="1.6" opacity="0.91"/>
    <circle cx="0" cy="0" r="8" fill="none" stroke="#f72585" stroke-width="1.8" opacity="0.96"/>
    <circle cx="0" cy="0" r="4" fill="none" stroke="#f72585" stroke-width="2" opacity="1"/>
    <circle cx="0" cy="0" r="2" fill="none" stroke="#ffd60a" stroke-width="1.2" stroke-dasharray="2,1.5" opacity="0.9"/>
    <circle cx="0" cy="0" r="0.8" fill="#ffd60a"/>
    <text x="0" y="105" font-family="'Courier New', monospace" font-size="9" fill="#f7258590" text-anchor="middle">n=1 → n=40</text>
    <text x="0" y="118" font-family="'Courier New', monospace" font-size="8" fill="#ffffff40" text-anchor="middle">EXTREME artifacts</text>
  </g>
  <g transform="translate(450, 298)">
    <circle cx="-160" cy="0" r="4" fill="none" stroke="#ffd60a" stroke-width="1.5" stroke-dasharray="2,1.5"/>
    <text x="-150" y="4" font-family="'Courier New', monospace" font-size="9" fill="#ffd60a80">Mathematical limit r=1</text>
    <circle cx="60" cy="0" r="3" fill="#ffd60a"/>
    <text x="70" y="4" font-family="'Courier New', monospace" font-size="9" fill="#ffd60a80">Attractor point</text>
  </g>
</svg>
CVIZEOF

echo "✅ convergence-viz.svg created"

# ============================================================
# 3. README.md
# ============================================================
cat > README.md << 'READMEEOF'
<div align="center">

![Banner](assets/banner.svg)

<br/>

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.18761718.svg)](https://doi.org/10.5281/zenodo.18761718)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=flat-square)](https://opensource.org/licenses/MIT)
[![OpenAIRE](https://img.shields.io/badge/Indexed-OpenAIRE-4cc9f0?style=flat-square)](https://explore.openaire.eu/search/result?pid=10.5281/zenodo.18761718)
[![Version](https://img.shields.io/badge/Version-v3-00f5d4?style=flat-square)](https://doi.org/10.5281/zenodo.18761718)
[![Published](https://img.shields.io/badge/Published-Feb%2025%202026-white?style=flat-square)](https://doi.org/10.5281/zenodo.18761718)

[![JavaScript](https://img.shields.io/badge/JavaScript-IEEE%20754-f7df1e?style=flat-square&logo=javascript&logoColor=black)](https://github.com/rishavjha8515-hub/iterated-root-convergence-visualization)
[![HTML5](https://img.shields.io/badge/HTML5-Canvas-e34f26?style=flat-square&logo=html5&logoColor=white)](https://github.com/rishavjha8515-hub/iterated-root-convergence-visualization)
[![Browser](https://img.shields.io/badge/Browser-Based-4cc9f0?style=flat-square&logo=googlechrome&logoColor=white)](https://github.com/rishavjha8515-hub/iterated-root-convergence-visualization)
[![Comprehension](https://img.shields.io/badge/Comprehension%20Gain-92%25-f72585?style=flat-square)](https://doi.org/10.5281/zenodo.18761718)
[![Zero Install](https://img.shields.io/badge/Install-Zero-00f5d4?style=flat-square)](https://github.com/rishavjha8515-hub/iterated-root-convergence-visualization)

<br/>

> *Standard calculators display* `127^(1/35) = 1.000000000` *— suggesting complete convergence.*
> *Theoretical analysis predicts deviation ≈ 0.138 — eight orders of magnitude above display precision.*
> **This visualization makes that contradiction visible.**

</div>

---

## 📄 Paper

**Visualizing Floating-Point Artifacts in Slowly Converging Sequences: A Geometric Approach**
*Jha, Rishav Anand Kumar — Independent Researcher, Mumbai, India*
Published: February 25, 2026 · Version v3 · OpenAIRE Indexed

| Resource | Link |
|---|---|
| 📦 Zenodo (DOI) | [10.5281/zenodo.18761718](https://doi.org/10.5281/zenodo.18761718) |
| 🐙 GitHub | [iterated-root-convergence-visualization](https://github.com/rishavjha8515-hub/iterated-root-convergence-visualization) |
| 🌐 OpenAIRE | [View Record](https://explore.openaire.eu/search/result?pid=10.5281/zenodo.18761718) |
| 👤 ORCID | [0009-0008-4552-4154](https://orcid.org/0009-0008-4552-4154) |

---

## 🌀 The Core Idea

The limit lim N^(1/n) = 1 as n→∞ is elementary in analysis.
Yet its **numerical behavior is deeply counterintuitive.**

```
127^(1/10) = 1.7013       ← clearly not 1
127^(1/20) = 1.3044       ← still not 1
127^(1/35) = 1.000000000  ← calculator says: DONE ✓
                             theory says: deviation ≈ 0.138 ✗
```

This project encodes each iterate as the **radius of a concentric circle** — transforming convergence from a number into a shape you can *see*.

---

## 🎨 Visualization

<div align="center">

![Four Convergence Families](assets/convergence-viz.svg)

*Four convergence families rendered as concentric circles. The dashed gold ring marks the mathematical limit r=1.*
*Visual density directly reflects artifact severity — more circles = slower convergence = worse numerical deception.*

</div>

---

## ✨ Features

| Feature | Description |
|---|---|
| 🟢 **Geometric Encoding** | Each iterate N^(1/n) = radius of a circle. Convergence becomes spatial. |
| 🔍 **Adaptive Zoom** | Rescales as values approach 1. Visual resolution preserved after numerical stabilization. |
| 🎞️ **Animated Iteration** | Circles build dynamically — mirroring the mathematical process. |
| 📊 **4 Convergence Families** | Algebraic · Logarithmic · Exponential · Doubly-slow side by side. |
| 📤 **CSV Export** | All numerical values exportable for independent verification. |
| 🧮 **Theoretical Validation** | < 6% relative error vs theory for n ≥ 40. |
| 🌐 **Zero Install** | Runs in any modern browser. Open the file. That's it. |

---

## 🧠 Why It Matters

```
Algebraic   1/n       → needs ~10^10 iterations for display precision  ← SEVERE
Logarithmic ln(n)/n   → needs ~10^11 iterations                        ← SEVERE
Doubly-slow 1/nln(n)  → needs ~10^13 iterations                        ← EXTREME
Exponential e^(-n)    → needs only 24 iterations                       ← minimal
```

**Practical impact:** Iterative solvers, Monte Carlo methods, and gradient descent all exhibit slow convergence. Stopping when a display reads "done" may mean stopping 10 billion iterations too early.

---

## 📊 Empirical Validation

Preliminary pedagogical study — 12 high school students (ages 16–18):

```
Before: 17% correctly identified display precision as cause
After:  92% correctly explained the floating-point artifact
Gain:   +75 percentage points
```

> *"Seeing the circles continue shrinking even when the number showed 1.0 was eye-opening"*

---

## 🚀 Quick Start

```bash
git clone https://github.com/rishavjha8515-hub/iterated-root-convergence-visualization
cd iterated-root-convergence-visualization
open root_convergence.html   # No npm. No install. Just open.
```

---

## 🛠️ Implementation

```
Language:    JavaScript (client-side, IEEE 754 double-precision)
Rendering:   HTML5 Canvas
Performance: 60 FPS for n ≤ 100 on commodity hardware
Memory:      < 50 MB typical
Precision:   Practical depth n ~ 10^6 before underflow
```

---

## 📁 Repository Structure

```
iterated-root-convergence-visualization/
├── root_convergence.html           ← Interactive visualization (open this)
├── root_convergence_final_v1.pdf   ← Associated paper v3
├── assets/
│   ├── banner.svg                  ← Header banner
│   └── convergence-viz.svg         ← Four-panel visualization
└── README.md
```

---

## 📚 Citation

```bibtex
@software{jha2026floatingpoint,
  author    = {Jha, Rishav Anand Kumar},
  title     = {Visualizing Floating-Point Artifacts in Slowly
               Converging Sequences: A Geometric Approach},
  year      = {2026},
  publisher = {Zenodo},
  version   = {v3},
  doi       = {10.5281/zenodo.18761718},
  url       = {https://doi.org/10.5281/zenodo.18761718}
}
```

---

## 👨‍💻 Author

<div align="center">

**Rishav Anand Kumar Jha**
Independent Researcher · Mumbai, India

[![ORCID](https://img.shields.io/badge/ORCID-0009--0008--4552--4154-a6ce39?style=flat-square&logo=orcid)](https://orcid.org/0009-0008-4552-4154)
[![Email](https://img.shields.io/badge/Email-rishavjha8515%40gmail.com-ea4335?style=flat-square&logo=gmail&logoColor=white)](mailto:rishavjha8515@gmail.com)
[![GitHub](https://img.shields.io/badge/GitHub-rishavjha8515--hub-181717?style=flat-square&logo=github)](https://github.com/rishavjha8515-hub)

*Released under MIT License · Freely available for educational and research use*

</div>