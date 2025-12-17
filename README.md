🌀 Iterated Root Convergence — Interactive Visualization

Visual Discovery and Computational Validation of

\lim_{n \to \infty} N^{1/n} = 1

An interactive, browser-based visualization that reveals how iterated roots converge to unity — and why numerical computation often appears to stabilize prematurely due to finite precision.

🔗 Repository:
https://github.com/rishavjha8515-hub/iterated-root-convergence-visualization

📄 Associated Paper:
Visual Discovery and Computational Validation of Iterated Root Convergence
(Manuscript prepared for archival release on Zenodo)


---

📌 Overview

The limit

\lim_{n \to \infty} N^{1/n} = 1

is elementary in analysis, yet its numerical behavior is frequently counterintuitive. Standard calculators often display constant values (e.g. 1.00000000) beyond moderate iteration counts, creating the illusion of premature convergence.

This project originated from late-night calculator experimentation during physics exam preparation and evolved into a fully interactive computational tool that:

Makes convergence visually explicit

Reveals finite-precision artifacts

Bridges numerical computation with theoretical limits


Successive iterates are encoded as concentric circles, transforming temporal iteration into geometric contraction toward a universal attractor.


---

🎯 Key Features

🟢 Geometric Encoding
Each iterate  is rendered as the radius of a concentric circle.

🔍 Adaptive Zoom
Automatically rescales the view as values approach unity, preserving visual distinguishability even after numerical stabilization.

🎞️ Animated Iteration
Iterates are constructed dynamically, mirroring the underlying mathematical process.

📤 Data Export
Numerical values can be exported as CSV for independent analysis and verification.

🧮 Theoretical Validation
Observed numerical errors agree with the asymptotic prediction


|N^{1/n} - 1| \approx \frac{\ln N}{n}


---

🧠 Why This Matters

Numerical computation strongly shapes mathematical intuition — sometimes incorrectly.

This visualization clarifies:

Why calculators show apparent stabilization long before true convergence

How finite display precision differs from mathematical limits

Why algebraic (1/n) decay remains visually relevant over long iteration ranges


The tool is designed for learning, exploration, and teaching, not merely demonstration.


---

🛠️ Implementation Details

Language: JavaScript (client-side)

Rendering: HTML5 Canvas

Arithmetic: IEEE 754 double-precision floating point

Framework: React

Execution: Fully browser-based (no installation required)


Adaptive zoom affects only visualization scale — numerical computations remain unchanged and exportable.


---

📊 Reproducibility

All figures, tables, and numerical results in the accompanying manuscript can be regenerated using this repository.

The project is released under the MIT License to encourage reuse in educational and research settings.


---

📚 Citation (to be updated)

A formal citation entry and DOI will be added here after Zenodo publication.

Proposed citation format (pending DOI):

Jha, R. A. K. Visual Discovery and Computational Validation of Iterated Root Convergence. Zenodo.


---

🏷️ Tags

mathematics
numerical-analysis
limits
mathematical-visualization
computational-mathematics
education
floating-point
convergence
interactive-visualization


---

🧑‍💻 Author

Jha Rishav Anand Kumar
Independent Researcher
📧 rishavjha8515@gmail.com

----
