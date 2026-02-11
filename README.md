# ⚛️ Quantum Field Imaging
## A Unified Theory of Parallel Quantum Metrology

**Author**: Jyh-Long Chern  
**Book Plan Version**: v2.1 (Production-Ready Framework)  
**Status**: 🟢 Active Development — All 17 Chapters Drafted

> 📘 These notes continue my public learning series: *[The Eikonal Bridge](https://github.com/jlchern-251016/eikonal-bridge)* connected classical optics to quantum photonics; this work connects quantum metrology to computational imaging.

---

## 🔭 Overview

This repository contains the complete manuscript, simulation code, and companion materials for *Quantum Field Imaging (QFI)*, an open-source technical book that establishes QFI as a distinct discipline bridging quantum sensing with classical optical engineering.

The central thesis is captured by the **two-layer taxonomy**:

| Layer | Definition | Output |
|-------|-----------|--------|
| 🔬 **Quantum Field Metrology (QFM)** | Parallel quantum measurement of physical fields | Field map **F**(**r**) |
| 🔭 **Quantum Field Imaging (QFI)** | QFM + source reconstruction + uncertainty quantification | Source estimate **Ŝ**(**r**) ± σ_S(**r**) |

> ⚡ *Without reconstruction, a system is QFM. With reconstruction and uncertainty quantification, it becomes QFI.*

---

## 🔗 The QFI Operator Stack

The complete QFI pipeline is described by a seven-operator chain:

```
S  →  G  →  F  →  M  →  D  →  R  →  Ŝ
```

| Icon | Operator | Name | Role |
|------|----------|------|------|
| 🎯 | **S** | Source | Physical quantity to be imaged (e.g., current density **J**(**r**)) |
| 🧲 | **G** | Forward Model | Physics mapping source to field (e.g., Biot–Savart) |
| 🌊 | **F** | Field | Observable physical field (e.g., **B**(**r**)) |
| 📷 | **M** | Measurement | Optical + quantum sensing system |
| 💾 | **D** | Data | Raw measurement output (pixel array) |
| 🔄 | **R** | Reconstruction | Inverse problem solver |
| ✅ | **Ŝ** | Estimate | Reconstructed source with uncertainty bounds |

---

## 📐 The QFI Imaging Figure of Merit

```
Q_IFOM  =  Q_FOM  ×  Γ_inv  ×  Γ_mm
```

| Symbol | Name | Definition | Range |
|--------|------|-----------|-------|
| 📊 **Q_FOM** | Measurement throughput | (η_q / η_classical) × (N_parallel / t_acq) × Φ_multi | [s⁻¹] |
| 🎯 **Γ_inv** | Reconstruction fidelity | CRB / MSE_achieved | (0, 1] |
| ⚖️ **Γ_mm** | Model-mismatch penalty | Π(1 − ε_i²) | (0, 1] |

---

## 📖 Book Structure

The book is organized in **six parts** across **17 chapters**, following the QFI operator stack from theory through implementation to application.

### 🏗️ Part I — Theoretical Foundations

| Ch | Title | Operator | Key Contributions |
|----|-------|----------|-------------------|
| 1 | 🌅 The QFI Paradigm | All (S→Ŝ) | QFM/QFI taxonomy, Q_IFOM definition, CCD-to-QFI historical parallel |
| 2 | 📏 Fundamental Limits in QFI | All | Cramér–Rao bound, QFI uncertainty principle, multi-physics conditioning theorem |

### 🔦 Part II — Optical System Design

| Ch | Title | Operator | Key Contributions |
|----|-------|----------|-------------------|
| 3 | 💡 Illumination Engineering for QFI | M (optical) | Beam reshaping, TIRF theory, structured illumination, ε_illum < 3% |
| 4 | 🔍 Collection Optics for QFI | M (optical) | Objective design, PSF engineering, ε_PSF < 5% |
| 5 | 🌈 Spectral Filtering and Photon Management | M (optical) | Filter design, dichroic optimization, throughput budget |
| 6 | 📡 The Quantum Optical Transfer Function | M (optical) | Q-OTF formalism, Q-OTF → Γ_inv connection |

### 💎 Part III — Quantum Sensor Physics

| Ch | Title | Operator | Key Contributions |
|----|-------|----------|-------------------|
| 7 | ⚛️ NV Center Physics from First Principles | M (quantum) | Ground-state Hamiltonian, multi-physics response, η_q derivation |
| 8 | 🎵 Pulse Sequences for Multi-Physics Sensing | M (quantum) | Ramsey, Hahn echo, dynamical decoupling, Φ_multi optimization |
| 9 | 📸 Wide-Field ODMR and Camera Integration | M (quantum) | Ensemble ODMR, camera selection, ε_PRNU < 2% |

### 🧲 Part IV — Forward Models

| Ch | Title | Operator | Key Contributions |
|----|-------|----------|-------------------|
| 10 | 🧭 Magnetic Forward Models | G | Biot–Savart kernel, conditioning analysis, κ(G_B) bounds |
| 11 | 🔀 Multi-Physics Forward Models | G | G_multi = [G_B; G_T; G_ε], conditioning theorem, depth disambiguation |

### ⚙️ Part V — System Integration

| Ch | Title | Operator | Key Contributions |
|----|-------|----------|-------------------|
| 12 | 🏭 QFI System Architecture | G + M | End-to-end Q_IFOM budget, photon budget cascade, error budget waterfall, FCN framework |
| 13 | 📐 Standoff Distance and Depth Sectioning | G | Standoff optimization, Γ_mm vs. standoff error curves |

### 🎯 Part VI — Reconstruction and Applications

| Ch | Title | Operator | Key Contributions |
|----|-------|----------|-------------------|
| 14 | 🔄 Inverse Problems and Reconstruction Algorithms | R | Tikhonov/TV/L1 regularization, Fisher information, Γ_inv optimization, Bayesian UQ |
| 15 | ⚡ Current Density Reconstruction | R | Fourier-space B→J inversion, 3D CDR, CAD-informed priors, production parameter lock |
| 16 | 🔬 Semiconductor Failure Analysis Applications | All | Short/open detection, hot spot localization, Q_IFOM benchmarking |
| 17 | 🚀 Future Directions and Emerging Frontiers | All | Entanglement-enhanced sensing, QEC for metrology, neuromorphic QFI, roadmap to Γ_inv → 1 |

---

## 💡 Key Technical Innovations

| # | Innovation | Description |
|---|-----------|-------------|
| 1 | 🏷️ **Two-Layer Taxonomy** | Clear QFM vs. QFI distinction — the inverse problem is the defining characteristic |
| 2 | 📡 **Q-OTF Formalism** | Classical OTF extended to quantum sensor arrays; spatial bandwidth → Γ_inv |
| 3 | 🔗 **Complete Operator Stack** | S→G→F→M→D→R→Ŝ as unified design language |
| 4 | 📊 **Q_IFOM Figure of Merit** | Single equation capturing all subsystem contributions multiplicatively |
| 5 | 🔀 **Multi-Physics Conditioning Theorem** | κ(G_multi) < κ(G_single) — depth disambiguation via physics fusion |
| 6 | 🎯 **Reconstruction Fidelity Framework** | Γ_inv, Γ_mm metrics with golden sample validation and falsification protocols |

---

## 💎 Exemplar Platform: NV Centers in Diamond

The book uses nitrogen-vacancy (NV) centers in diamond as the primary QFI platform:

| Physics Channel | 🧲 Response Mechanism | 📏 Typical Sensitivity |
|----------------|----------------------|----------------------|
| Magnetic field **B** | Zeeman splitting | ~1 nT/√Hz (ensemble) |
| Temperature **T** | Zero-field splitting shift | ~10 mK/√Hz |
| Strain **ε** | Crystal field coupling | ~10⁻⁶/√Hz |
| Electric field **E** | Stark effect | ~200 V/cm/√Hz |

> 💡 Multi-physics capability enables Φ_multi > 1, providing fundamental advantages for buried source reconstruction.

---

## ✅ QFI Gate Checklist

For any system claiming to be "QFI" (not just QFM), verify:

- [ ] 🎯 Source estimate Ŝ(**r**) provided (not just field map F(**r**))
- [ ] 📏 Uncertainty bounds σ_S(**r**) computed and reported
- [ ] 📊 Reconstruction residual ‖D − M·G·Ŝ‖ computed
- [ ] 🔍 Residual passes whiteness test (no systematic patterns)
- [ ] ✅ Golden sample validation performed with Γ_inv > 0.85
- [ ] 📋 Falsification tests documented

> ⚠️ **If any box is unchecked → System is QFM, not QFI.**

---

## 🗂️ Repository Structure

```
Quantum-Field-Imaging/
│
├── 📄 README.md
│
├── 📁 chapters/
│   ├── ch01_qfi_paradigm.tex           🌅
│   ├── ch02_fundamental_limits.tex      📏
│   ├── ch03_illumination_engineering.tex 💡
│   ├── ch04_collection_optics.tex       🔍
│   ├── ch05_spectral_filtering.tex      🌈
│   ├── ch06_quantum_otf.tex             📡
│   ├── ch07_nv_center_physics.tex       ⚛️
│   ├── ch08_pulse_sequences.tex         🎵
│   ├── ch09_widefield_odmr.tex          📸
│   ├── ch10_magnetic_forward_models.tex  🧭
│   ├── ch11_multiphysics_forward_models.tex 🔀
│   ├── ch12_system_architecture.tex      🏭
│   ├── ch13_standoff_depth.tex           📐
│   ├── ch14_reconstruction_algorithms.tex 🔄
│   ├── ch15_current_density_reconstruction.tex ⚡
│   ├── ch16_semiconductor_fa_applications.tex  🔬
│   └── ch17_future_directions.tex        🚀
│
├── 📁 figures/
│   ├── ch01/ ... ch17/
│
├── 📁 simulations/
│   └── (Python simulation code per chapter)
│
└── 📁 docs/
    ├── QFI_Book_Plan_v2.1.md
    └── QFI_Style_Guide_v1.md
```

---

## 🧮 Mathematical Conventions

| Symbol | Icon | Meaning |
|--------|------|---------|
| Q_FOM | 📊 | QFM figure of merit (measurement throughput) |
| Q_IFOM | 🏆 | QFI imaging figure of merit (includes reconstruction) |
| η_q | ⚛️ | Quantum sensitivity |
| N_parallel | 📷 | Number of parallel measurement channels |
| Φ_multi | 🔀 | Multi-physics correlation factor |
| Γ_inv | 🎯 | Reconstruction fidelity |
| Γ_mm | ⚖️ | Model-mismatch penalty |
| κ(G) | 🔢 | Condition number of forward model |
| CRB | 📏 | Cramér–Rao Bound |

---

## 🎓 Target Audience

| Audience | 🔑 What you'll find |
|----------|---------------------|
| 🔭 **Optical Engineers** | System design, photon budgets, OTF/PSF analysis, design rules |
| ⚛️ **Quantum Physicists** | NV physics, pulse sequences, quantum advantage quantification |
| 🔬 **Semiconductor FA Engineers** | Current imaging, defect detection, production metrology |
| 📚 **Graduate Students** | First-principles development, worked examples, end-of-chapter problems |
| ⚙️ **Instrument Developers** | Figures of merit, error budgets, calibration protocols |

---

## 🧭 How to Navigate This Book

| 🎯 Your goal | 📖 Read these chapters |
|-------------|----------------------|
| Conceptual overview | Ch. 1–2 (QFM/QFI framework + fundamental limits) |
| Optical system design | Ch. 3–6 (illumination → collection → filtering → Q-OTF) |
| Quantum sensor development | Ch. 7–9 (NV physics → pulse sequences → wide-field ODMR) |
| Forward modeling | Ch. 10–11 (magnetic + multi-physics operators) |
| System integration | Ch. 12–13 (architecture + standoff optimization) |
| Reconstruction & applications | Ch. 14–17 (algorithms → CDR → semiconductor FA → future) |

---

## 📎 Design Rules at a Glance

Each chapter contributes quantitative design rules:

> **DR X.Y**: *[Specification with quantitative threshold and operating conditions]*

| Category | Example Rules | Chapters |
|----------|--------------|----------|
| 🔦 Optical | ε_illum < 3%, ε_PSF < 5% | 3–6 |
| 💎 Quantum | NV density 1–5 ppm, T₂ optimization | 7–9 |
| 🧲 Forward model | κ(G) bounds, conditioning requirements | 10–11 |
| ⚙️ System | End-to-end Γ_mm budget, calibration intervals | 12–13 |
| 🎯 Reconstruction | Γ_inv > 0.85 target, regularization selection | 14–15 |

---

## 📌 Relation to The Eikonal Bridge

This project is a companion to [The Eikonal Bridge: From Classical Lens Design to Quantum Photonics Through Differentiable Computing](https://github.com/jlchern-251016/eikonal-bridge):

| Aspect | 🌉 The Eikonal Bridge | ⚛️ Quantum Field Imaging |
|--------|----------------------|-------------------------|
| **Scope** | Classical → quantum optics | Quantum metrology → computational imaging |
| **Core tool** | Differentiable ray tracing | Operator stack S→G→F→M→D→R→Ŝ |
| **Key equation** | Eikonal equation ‖∇φ‖ = n(**r**) | Q_IFOM = Q_FOM × Γ_inv × Γ_mm |
| **Application** | Lens design optimization | Semiconductor failure analysis |
| **Bridge** | Connects ray optics to wave optics to quantum photonics | Connects quantum sensing to inverse problems to production metrology |

---

## 📝 Citation

```bibtex
@book{chern2025qfi,
  author    = {Chern, Jyh-Long},
  title     = {Quantum Field Imaging: A Unified Theory of Parallel Quantum Metrology},
  year      = {2025},
  url       = {https://github.com/jlchern-251016/Quantum-Field-Imaging}
}
```

---

## 📜 License

This project is released as an open-source educational resource. Please see the LICENSE file for details.

---

## 🤝 Acknowledgments

Contributions, feedback, and collaboration inquiries are welcome. This work aims to establish QFI as a citable reference framework bridging fundamental quantum physics with production-grade metrology engineering.

---

*⚛️ Quantum Field Imaging — from quantum states to engineering decisions.*



— The QFI Gate Criterion
