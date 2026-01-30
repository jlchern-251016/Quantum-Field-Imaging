# Quantum Field Imaging
## A Unified Theory of Parallel Quantum Metrology and Inverse Source Reconstruction

[![License: CC BY-NC-SA 4.0](https://img.shields.io/badge/License-CC%20BY--NC--SA%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc-sa/4.0/)
[![LaTeX](https://img.shields.io/badge/Made%20with-LaTeX-1f425f.svg)](https://www.latex-project.org/)
[![Python 3.8+](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![Book Version](https://img.shields.io/badge/Version-2.1-green.svg)]()

---

## Overview

**Quantum Field Imaging (QFI)** establishes a new discipline at the intersection of classical optics and quantum sensing. This open-source textbook provides a rigorous, unified theoretical framework for parallel quantum metrology with inverse source reconstruction capabilities—addressing critical throughput bottlenecks in semiconductor failure analysis and beyond.

### The Central Problem

Modern semiconductor metrology faces a fundamental challenge: achieving nanometer-scale spatial resolution while maintaining the throughput demands of production environments. Classical approaches hit physical limits. Single-point quantum sensors achieve remarkable sensitivity but sacrifice parallelism. **QFI bridges this gap through parallel measurement with physics-based source reconstruction.**

---

## The Two-Layer Taxonomy

This book introduces a critical distinction that forms the conceptual backbone of the entire framework:

| Layer | System Type | Output | Key Characteristic |
|-------|-------------|--------|-------------------|
| **Quantum Field Metrology (QFM)** | Parallel quantum sensing | Calibrated field map F(r) with uncertainty σ_F(r) | Measurement only |
| **Quantum Field Imaging (QFI)** | QFM + Inverse reconstruction | Source estimate Ŝ(r) with uncertainty σ_S(r) | Forward model + Reconstruction required |

### The QFI Gate Criterion

A system qualifies as QFI **if and only if** it delivers:
1. Source estimate Ŝ(r)
2. Uncertainty bounds σ_S(r)
3. Reconstruction residual ||D - M·G·Ŝ||
4. Falsification test results

**Missing any of these → the system is QFM, not QFI.**

---

## The Operator Stack Framework

The book organizes QFI systems through a complete operator chain:

```
S → G → F → M → D → R → Ŝ
```

| Operator | Name | Function |
|----------|------|----------|
| **S** | Source | Hidden source distribution to be reconstructed |
| **G** | Forward Model | Physics mapping source to field (Biot-Savart, heat diffusion, etc.) |
| **F** | Field | Physical field at sensor plane |
| **M** | Measurement | Optical + quantum system (collection, filtering, detection) |
| **D** | Data | Raw measurement data |
| **R** | Reconstruction | Inverse algorithm (regularization, optimization, ML) |
| **Ŝ** | Estimate | Reconstructed source with uncertainty |

---

## Key Figures of Merit

### QFM Figure of Merit (Measurement Throughput)
```
Q_FOM = (η_q / η_classical) × (N_parallel / t_acquisition) × Φ_multi
```

### QFI Imaging Figure of Merit (Complete System)
```
Q_IFOM = Q_FOM × Γ_inv × Γ_mm
```

Where:
- **Γ_inv**: Reconstruction fidelity factor (0 < Γ_inv ≤ 1) — how well R recovers S
- **Γ_mm**: Model-mismatch penalty (0 < Γ_mm ≤ 1) — accuracy of forward model G
- **Φ_multi**: Multi-physics correlation factor — information gain from combined measurements

---

## Book Structure (v2.1)

The book is organized into **six parts** spanning **17 chapters**:

### Part I: Theoretical Foundations
| Ch | Title | Operator Focus | Key Content |
|----|-------|----------------|-------------|
| 1 | The QFI Paradigm | All | QFM/QFI taxonomy, Q_IFOM framework, operator stack |
| 2 | Fundamental Limits in QFI | M, R limits | Cramér-Rao bound, uncertainty quantification, multi-physics conditions |

### Part II: Optical System Design
| Ch | Title | Operator Focus | Key Content |
|----|-------|----------------|-------------|
| 3 | Illumination Engineering | M | Étendue, TIRF, uniformity theory, ε_illum specification |
| 4 | Collection Optics | M | NA optimization, PSF engineering, ε_PSF specification |
| 5 | Spectral Filtering | M | NV emission filtering, throughput optimization |
| 6 | Quantum Optical Transfer Function | M | Q-OTF formalism, connection to Γ_inv |

### Part III: Quantum Sensor Physics
| Ch | Title | Operator Focus | Key Content |
|----|-------|----------------|-------------|
| 7 | NV Center Physics | M | Level structure, ODMR, η_q derivation, multi-physics basis |
| 8 | Pulse Sequences | M | Ramsey, Hahn echo, dynamical decoupling, Φ_multi optimization |
| 9 | Wide-Field ODMR | M | Camera integration, PRNU, ε_PRNU specification |

### Part IV: Forward Models
| Ch | Title | Operator Focus | Key Content |
|----|-------|----------------|-------------|
| 10 | Magnetic Forward Models | G | Biot-Savart kernel, G_B construction, conditioning analysis |
| 11 | Multi-Physics Forward Models | G | Thermal, strain coupling, G_multi = [G_B; G_T; G_ε], conditioning theorem |

### Part V: System Integration
| Ch | Title | Operator Focus | Key Content |
|----|-------|----------------|-------------|
| 12 | QFI System Architecture | G + M | Probe station integration, calibration procedures, end-to-end Γ_mm |
| 13 | Standoff Distance and Depth Sectioning | G | Standoff optimization, depth disambiguation, ε_standoff tolerance |

### Part VI: Reconstruction and Applications
| Ch | Title | Operator Focus | Key Content |
|----|-------|----------------|-------------|
| 14 | Inverse Problems and Reconstruction | R | Tikhonov, TV, L1 regularization, Γ_inv optimization, uncertainty propagation |
| 15 | Current Density Reconstruction | R | B→J inversion, multi-physics J reconstruction, algorithm comparison |
| 16 | Semiconductor FA Applications | All | IC fault localization, production validation, Q_IFOM benchmarks |
| 17 | Future Directions | All | ML-based R operators, roadmap to Γ_inv → 1 |

---

## Error Budget Framework

The book develops a systematic error budget approach linking component specifications to system performance:

| Error Source | Symbol | Typical Spec | Affects |
|--------------|--------|--------------|---------|
| Standoff calibration | ε_standoff | < 5% | Γ_mm |
| PSF accuracy | ε_PSF | < 5% | Γ_mm |
| Illumination uniformity | ε_illum | < 3% | Γ_mm |
| MW field uniformity | ε_MW | < 5% | Γ_mm |
| Pixel response (PRNU) | ε_PRNU | < 2% | Γ_mm |

**Model-mismatch penalty**: Γ_mm = ∏(1 - εᵢ²) ≈ 1 - Σεᵢ²

---

## Repository Structure

```
quantum-field-imaging/
├── README.md
├── LICENSE
├── CONTRIBUTING.md
├── CHANGELOG.md
├── chapters/
│   ├── ch01_qfi_paradigm/
│   │   ├── chapter_01.tex
│   │   └── figures/
│   ├── ch02_fundamental_limits/
│   ├── ch03_illumination/
│   ├── ...
│   └── ch17_future_directions/
├── simulations/
│   ├── ch01_problems/
│   ├── ch02_problems/
│   └── ...
├── style/
│   ├── qfi_preamble.tex
│   ├── qfi_commands.tex
│   └── qfi_style_guide.md
├── bibliography/
│   └── qfi_references.bib
└── build/
    └── (compiled PDFs)
```

---

## Getting Started

### Prerequisites

**For reading**: PDF viewer

**For compilation**:
- LaTeX distribution (TeX Live 2022+ or MiKTeX)
- Python 3.8+ with NumPy, SciPy, Matplotlib

### Quick Start

```bash
# Clone the repository
git clone https://github.com/[username]/quantum-field-imaging.git
cd quantum-field-imaging

# Compile a single chapter
cd chapters/ch01_qfi_paradigm
pdflatex chapter_01.tex
bibtex chapter_01
pdflatex chapter_01.tex
pdflatex chapter_01.tex

# Run problem simulations
cd ../../simulations/ch01_problems
python problem_solutions.py
```

---

## Target Audience

| Audience | Background | Primary Focus |
|----------|------------|---------------|
| **Optical Engineers** | Classical optics, lens design | Q-OTF formalism, M operator design |
| **Quantum Physicists** | QM, atomic physics | NV physics, Φ_multi, decoherence |
| **FA Engineers** | Semiconductor testing | Chapters 13, 15, 16; production integration |
| **Algorithm Developers** | Inverse problems, ML | Chapters 2, 14; R operator design |
| **Graduate Students** | Physics/EE fundamentals | Complete theory with worked examples |

---

## Key Features

- **First-principles derivations** with complete mathematical development
- **Two-layer QFM/QFI taxonomy** distinguishing measurement from imaging
- **Operator stack framework** for systematic system decomposition
- **Quantitative design rules** with operational specifications
- **Multi-physics correlation** achieving 2-5× improvement in Γ_inv
- **Worked examples** with numerical calculations throughout
- **Python simulations** for all chapters with reproducible results
- **Problem sets** with solution hints for self-study

---

## Design Philosophy

1. **The field is not the image**: True imaging requires reconstruction
2. **Operational definitions**: All metrics defined by measurement procedures
3. **Quantitative specifications**: Concrete numbers, not vague guidelines
4. **Complete derivations**: Rigor without obscurity
5. **Open and reproducible**: All code included and documented

---

## Contributing

Contributions welcome! See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

### Ways to Contribute
- Report errors via Issues
- Improve derivations or explanations
- Add worked examples
- Enhance simulation code
- Translate chapters

### Code Standards
- Python: PEP 8, ASCII-only encoding (Windows compatible)
- LaTeX: Follow `style/qfi_style_guide.md`

---

## Citation

```bibtex
@book{chern2026qfi,
  title     = {Quantum Field Imaging: A Unified Theory of Parallel 
               Quantum Metrology and Inverse Source Reconstruction},
  author    = {Chern, Jyh-Long},
  year      = {2026},
  version   = {2.1},
  publisher = {Open Source},
  url       = {https://github.com//jlchern-251016/quantum-field-imaging}
}
```

---

## License

- **Book content**: [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)
- **Simulation code**: [MIT License](LICENSE-CODE)

---

## Acknowledgments

This work builds upon foundational contributions in quantum sensing, optical metrology, inverse problems, and semiconductor failure analysis. The QFI framework synthesizes insights from the quantum diamond community, optical engineering practice, and production metrology requirements.

---
---

*"If your deliverable is only F(r), you are doing QFM. You are doing QFI if and only if you deliver Ŝ(r) with uncertainty bounds."*

— The QFI Gate Criterion
