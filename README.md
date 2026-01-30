# Quantum Field Imaging
## A Unified Theory of Parallel Quantum Metrology

[![License: CC BY-NC-SA 4.0](https://img.shields.io/badge/License-CC%20BY--NC--SA%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc-sa/4.0/)
[![LaTeX](https://img.shields.io/badge/Made%20with-LaTeX-1f425f.svg)](https://www.latex-project.org/)
[![Python 3.8+](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)

---

## Overview

**Quantum Field Imaging (QFI)** establishes a new discipline at the intersection of classical optics and quantum sensing. This open-source textbook provides a rigorous, unified theoretical framework for parallel quantum metrology with source reconstruction capabilities—addressing critical throughput bottlenecks in semiconductor failure analysis and beyond.

### The Central Problem

Modern semiconductor metrology faces a fundamental challenge: achieving nanometer-scale spatial resolution while maintaining the throughput demands of production environments. Classical approaches hit physical limits. Single-point quantum sensors achieve remarkable sensitivity but sacrifice parallelism. **QFI bridges this gap.**

### The Two-Layer Taxonomy

This book introduces a critical distinction:

| Layer | Approach | Output | Reconstruction |
|-------|----------|--------|----------------|
| **Quantum Field Metrology (QFM)** | Parallel quantum sensing | Field maps at sensor plane | None |
| **Quantum Field Imaging (QFI)** | QFM + Physics-based inversion | Reconstructed source distribution | Forward model required |

The key insight: **True imaging requires reconstruction.** A field map is not an image until you solve the inverse problem to recover the hidden source.

---

## Key Features

- **First-principles derivations** from quantum mechanics to system design
- **Quantum Optical Transfer Function (Q-OTF)** formalism bridging classical optics and quantum sensing
- **Operator stack framework** (S→G→F→M→D→R→Ŝ) for systematic system decomposition
- **Multi-physics correlation** techniques achieving 2-5× improvement in reconstruction fidelity
- **Quantitative design rules** for production-grade system specifications
- **NV centers in diamond** as the exemplar platform (room-temperature, multi-physics, optical readout)
- **Worked examples** with numerical calculations and Python simulations
- **Problem sets** with solution hints for self-study and courses

---

## Book Structure

The book is organized into **six parts** spanning **17 chapters**:

### Part I: Foundations
- Chapter 1: Introduction to Quantum Field Imaging
- Chapter 2: Mathematical Preliminaries
- Chapter 3: Quantum Sensing Fundamentals

### Part II: Optical System Theory
- Chapter 4: Classical Optical Transfer Functions
- Chapter 5: Quantum Optical Transfer Function (Q-OTF)
- Chapter 6: Coherence and Correlation in Quantum Fields

### Part III: Quantum Sensor Physics
- Chapter 7: NV Center Physics and Engineering
- Chapter 8: Alternative Quantum Sensor Platforms
- Chapter 9: Noise, Decoherence, and Sensitivity Limits

### Part IV: System Design
- Chapter 10: Optical Collection and Delivery Systems
- Chapter 11: Parallel Readout Architectures
- Chapter 12: System Integration and Calibration

### Part V: Applications
- Chapter 13: Semiconductor Failure Analysis
- Chapter 14: Biomedical Imaging Applications
- Chapter 15: Materials Characterization

### Part VI: Advanced Topics
- Chapter 16: Quantum-Enhanced Reconstruction Algorithms
- Chapter 17: Future Directions and Emerging Platforms

---

## The QFI Figure of Merit

The book develops a comprehensive figure of merit framework:

```
Q_IFOM = Q_FOM × Γ_inv × Γ_mm
```

Where:
- **Q_FOM**: Quantum sensing figure of merit (sensitivity × bandwidth × parallelism)
- **Γ_inv**: Reconstruction fidelity factor
- **Γ_mm**: Model-mismatch penalty factor

This framework enables quantitative comparison across platforms and applications.

---

## Repository Structure

```
quantum-field-imaging/
├── README.md
├── LICENSE
├── chapters/
│   ├── ch01/
│   │   ├── chapter_01.tex
│   │   └── figures/
│   ├── ch02/
│   │   ├── chapter_02.tex
│   │   └── figures/
│   └── ...
├── simulations/
│   ├── ch01_problems/
│   ├── ch02_problems/
│   └── ...
├── style/
│   ├── qfi_preamble.tex
│   ├── qfi_commands.tex
│   └── qfi_colors.tex
├── bibliography/
│   └── qfi_references.bib
└── build/
    └── (compiled PDFs)
```

---

## Getting Started

### Prerequisites

**For reading:**
- PDF viewer

**For compilation:**
- LaTeX distribution (TeX Live 2022+ or MiKTeX)
- Python 3.8+ with NumPy, SciPy, Matplotlib

### Compilation

```bash
# Clone the repository
git clone https://github.com/[username]/quantum-field-imaging.git
cd quantum-field-imaging

# Compile a single chapter
cd chapters/ch01
pdflatex chapter_01.tex
bibtex chapter_01
pdflatex chapter_01.tex
pdflatex chapter_01.tex

# Or use the build script
./build.sh all
```

### Running Simulations

```bash
cd simulations/ch01_problems
python problem_solutions.py
# Outputs saved to timestamped directory
```

---

## Target Audience

This book is designed for:

| Audience | Background | Primary Interest |
|----------|------------|------------------|
| **Optical Engineers** | Classical optics, lens design | Q-OTF formalism, system integration |
| **Quantum Physicists** | Quantum mechanics, atomic physics | Multi-physics sensing, decoherence |
| **FA Engineers** | Semiconductor testing, failure analysis | Throughput, practical implementation |
| **Graduate Students** | Physics or EE fundamentals | Complete theory and applications |

---

## Design Philosophy

1. **Rigor without obscurity**: Complete derivations with physical intuition
2. **Theory meets practice**: Every concept tied to measurable quantities
3. **Operational definitions**: All metrics defined by measurement procedures
4. **Quantitative design rules**: Concrete specifications, not vague guidelines
5. **Open and reproducible**: All simulations included and documented

---

## Contributing

Contributions are welcome! Please see [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

### Ways to Contribute
- Report errors or typos via Issues
- Suggest improvements to derivations
- Add worked examples or problems
- Improve simulation code
- Translate chapters

### Code Style
- Python: PEP 8, ASCII-only encoding for Windows compatibility
- LaTeX: Follow `style/qfi_style_guide.md`

---

## Citation

If you use this book in your research or teaching, please cite:

```bibtex
@book{qfi2026,
  title     = {Quantum Field Imaging: A Unified Theory of Parallel Quantum Metrology and inverse source reconstruction},
  author    = {[Chern, Jyh-Long]},
  year      = {2026},
  publisher = {Open Source},
  url       = {https://github.com/[username]/quantum-field-imaging}
}
```

---

## License

This work is licensed under a [Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License](https://creativecommons.org/licenses/by-nc-sa/4.0/).

- **Attribution**: Give appropriate credit
- **NonCommercial**: Not for commercial purposes without permission
- **ShareAlike**: Derivatives under same license

Simulation code is released under the [MIT License](LICENSE-CODE).

---

## Acknowledgments

This book builds upon decades of foundational work in quantum sensing, optical metrology, and inverse problems. Special thanks to the quantum diamond community and semiconductor metrology practitioners whose insights shaped this unified framework.

---

## Contact

- **Issues**: [GitHub Issues](https://github.com/[username]/quantum-field-imaging/issues)
- **Discussions**: [GitHub Discussions](https://github.com/[username]/quantum-field-imaging/discussions)

---

*"The field is not the image. The image emerges when we solve the inverse problem."*
