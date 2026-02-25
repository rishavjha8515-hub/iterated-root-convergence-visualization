<div align="center">

![Banner](assets/banner.svg)

<br/>

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.18761718.svg)](https://doi.org/10.5281/zenodo.18761718)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=flat-square)](https://opensource.org/licenses/MIT)
[![OpenAIRE](https://img.shields.io/badge/Indexed-OpenAIRE-4cc9f0?style=flat-square&logo=openaire)](https://explore.openaire.eu/search/result?pid=10.5281/zenodo.18761718)
[![Version](https://img.shields.io/badge/Version-v3-00f5d4?style=flat-square)](https://doi.org/10.5281/zenodo.18761718)
[![Published](https://img.shields.io/badge/Published-Feb%2025%202026-white?style=flat-square)](https://doi.org/10.5281/zenodo.18761718)

[![JavaScript](https://img.shields.io/badge/JavaScript-IEEE%20754-f7df1e?style=flat-square&logo=javascript&logoColor=black)](https://github.com/rishavjha8515-hub/iterated-root-convergence-visualization)
[![HTML5](https://img.shields.io/badge/HTML5-Canvas-e34f26?style=flat-square&logo=html5&logoColor=white)](https://github.com/rishavjha8515-hub/iterated-root-convergence-visualization)
[![Browser](https://img.shields.io/badge/Browser-Based-4cc9f0?style=flat-square&logo=googlechrome&logoColor=white)](https://github.com/rishavjha8515-hub/iterated-root-convergence-visualization)
[![Comprehension](https://img.shields.io/badge/Comprehension%20Gain-92%25-f72585?style=flat-square)](https://doi.org/10.5281/zenodo.18761718)
[![Zero Install](https://img.shields.io/badge/Install-Zero-00f5d4?style=flat-square&logo=checkmarx)](https://github.com/rishavjha8515-hub/iterated-root-convergence-visualization)

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

The limit $\lim_{n \to \infty} N^{1/n} = 1$ is elementary in analysis.  
Yet its **numerical behavior is deeply counterintuitive.**

```
127^(1/10) = 1.7013     ← clearly not 1
127^(1/20) = 1.3044     ← still not 1
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
| 🟢 **Geometric Encoding** | Each iterate $N^{1/n}$ = radius of a circle. Convergence becomes spatial. |
| 🔍 **Adaptive Zoom** | Rescales as values approach 1. Visual resolution preserved after numerical stabilization. |
| 🎞️ **Animated Iteration** | Circles build dynamically — mirroring the mathematical process. |
| 📊 **4 Convergence Families** | Algebraic · Logarithmic · Exponential · Doubly-slow — side by side. |
| 📤 **CSV Export** | All numerical values exportable for independent verification. |
| 🧮 **Theoretical Validation** | < 6% relative error vs $\|N^{1/n} - 1\| \approx \frac{\ln N}{n}$ for $n \geq 40$. |
| 🌐 **Zero Install** | Runs in any modern browser. Open the file. That's it. |

---

## 🧠 Why It Matters

Numerical computation shapes mathematical intuition — **sometimes incorrectly.**

```
Algebraic  1/n      → needs ~10^10 iterations for display precision  ← SEVERE
Logarithmic ln(n)/n → needs ~10^11 iterations                        ← SEVERE  
Doubly-slow 1/nln(n)→ needs ~10^13 iterations                        ← EXTREME
Exponential e^(-n)  → needs only 24 iterations                       ← minimal
```

**Practical impact:** Iterative solvers, Monte Carlo methods, and gradient descent all exhibit slow convergence. Stopping when a display reads "done" may mean stopping 10 billion iterations too early.

---

## 📊 Empirical Validation

Preliminary pedagogical study — 12 high school students (ages 16–18, calculus background):

```
Before: 17% correctly identified display precision as cause of apparent convergence
After:  92% correctly explained the floating-point artifact
Gain:   +75 percentage points
```

> *"Seeing the circles continue shrinking even when the number showed 1.0 was eye-opening"*

---

## 🚀 Quick Start

```bash
git clone https://github.com/rishavjha8515-hub/iterated-root-convergence-visualization
cd iterated-root-convergence-visualization
open root_convergence.html   # That's it. No npm. No install.
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

> Adaptive zoom affects **only rendering** — all numerical values remain unchanged and exportable.

---

## 📁 Repository Structure

```
iterated-root-convergence-visualization/
├── root_convergence.html          ← Interactive visualization (open this)
├── root_convergence_final_v1.pdf  ← Associated paper v3
├── assets/
│   ├── banner.svg                 ← Header banner
│   └── convergence-viz.svg        ← Four-panel visualization
├── data/
│   └── numerical_validation.csv   ← Table 1 & 2 data
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
