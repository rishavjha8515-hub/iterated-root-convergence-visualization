# Iterated Root Convergence Visualization

**Making a calculator's lie visible.**

DOI: [10.5281/zenodo.18761718](https://doi.org/10.5281/zenodo.18761718) · License: MIT · Version: v3 (February 2026)

Author: Rishav Anand Kumar Jha · ORCID: [0009-0008-4552-4154](https://orcid.org/0009-0008-4552-4154)

---

## Where this came from

I was pressing the root button on a calculator repeatedly — no particular reason, just curiosity. At the 37th root of a prime number, the display showed exactly 1. Permanently. No matter how many more times I pressed it.

But mathematically, N^(1/n) = 1 only when n → ∞. At n = 37, the true value is nowhere near 1.

Standard calculators display 127^(1/35) = 1.000000000 — suggesting complete convergence. Theoretical analysis predicts a deviation of ≈ 0.138 — eight orders of magnitude above display precision.

The calculator isn't broken. It's telling you the number rounded to its display limit. But that looks exactly like convergence. And if you're running an iterative algorithm and you stop when the screen says "done" — you may have stopped 10 billion iterations too early.

I wanted to make that contradiction visible. Not as a number. As a shape.

While mapping this systematically in a notebook on November 23, 2025, I noticed a pattern across integers 2 through 20:

- Primes (2, 3, 5, 7, 11, 13, 17, 19) → calculator saturates at the **37th root**
- Composites (4, 6, 8, 9, 10, 12, 14, 15, 16, 18, 20) → calculator saturates at the **38th root**

This is a preliminary observation, not a formal proof. It likely reflects how ln(N) differs between primes and composites relative to the calculator's display precision threshold. I haven't proven it holds generally — but it's consistent across everything I tested.

---

## The core idea

The limit lim(n→∞) N^(1/n) = 1 is elementary in analysis. Its numerical behavior is not.

```
127^(1/10)  = 1.7013      ← clearly not 1
127^(1/20)  = 1.3044      ← still not 1
127^(1/35)  = 1.000000000 ← calculator: DONE ✓
                             theory: deviation ≈ 0.138 ✗
```

Each iterate N^(1/n) gets encoded as the radius of a concentric circle. When the math converges, the circles collapse toward r=1. When the calculator lies about convergence, the circles keep shrinking — invisibly slow, but still moving.

The circles aren't a design choice. They're a consequence. Radius is the natural encoding of a number approaching 1 from above.

---

## What it shows

Four convergence families, side by side:

| Family | Rate | Iterations needed for display precision |
|--------|------|----------------------------------------|
| Algebraic (1/n) | slow | ~10¹⁰ |
| Logarithmic (ln(n)/n) | slower | ~10¹¹ |
| Doubly-slow (1/n·ln(n)) | very slow | ~10¹³ |
| Exponential (e^(-n)) | fast | ~24 |

The visual density reflects artifact severity directly — more circles, slower convergence, worse numerical deception.

---

## Why this matters beyond a curiosity

Iterative solvers, Monte Carlo methods, and gradient descent all exhibit slow convergence in practice. Stopping when a display reads "done" — or when a loss curve flattens to machine precision — may mean stopping far earlier than mathematical convergence actually requires.

This is a visualization of that failure mode.

---

## Theoretical validation

Approximation used: |N^(1/n) - 1| ≈ ln(N)/n for large n.

Relative error vs. this approximation: < 6% for n ≥ 40.

All numerical values are exportable as CSV for independent verification.

---

## Quick start

```bash
git clone https://github.com/rishavjha8515-hub/iterated-root-convergence-visualization
cd iterated-root-convergence-visualization
open root_convergence.html
```

No installation. No dependencies. Open the HTML file in any modern browser.

**Stack:** JavaScript (IEEE 754 double-precision) · HTML5 Canvas · 60 FPS for n ≤ 100 · zero external requirements.

---

## Repository structure

```
iterated-root-convergence-visualization/
├── root_convergence.html          ← open this
├── root_convergence_final_v1.pdf  ← paper (v3)
└── README.md
```

---
## Prime Saturation Paper

This repository also contains the reproducibility materials for:
"Prime Numbers Are Locally Logarithmically Minimal: A Device-Independent 
Saturation Phenomenon in Repeated Square Root Iteration"

Run: python saturation_analysis.py
Requires: matplotlib, numpy
## Paper

*Visualizing Floating-Point Artifacts in Slowly Converging Sequences: A Geometric Approach*
Jha, Rishav Anand Kumar — Independent Researcher, Mumbai, India
Published: February 25, 2026 · Version v3 · OpenAIRE Indexed

---

## Citation

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

*MIT License · © 2026 Rishav Anand Kumar Jha*
