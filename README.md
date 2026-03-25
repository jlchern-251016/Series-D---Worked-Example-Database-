# Series D — Worked-Example Database

**Explorer and Builder:** Jyh-Long Chern  
**Part of:** [Open-Source Engineering Optics Series](https://github.com/jlchern-251016)  
**Status:** see below

---

## What Is Series D?

Series D provides **complete, end-to-end worked examples** organized by formalism and by application domain. Each example walks from specification through analysis to result. Series D answers the question: *"Show me how this device works."*

D-series documents are **demonstrations, not derivations**. The full theoretical framework lives in Series B; the reusable toolkit functions live in Series C. D-series documents call C-series functions and validate them against B-series theory. They are the natural entry point for:

- **Industry engineers** who want to see a complete analysis before adapting it to their own device
- **Students** who learn best from worked examples
- **Community contributors** who want to add new devices or application domains

---

## Documents

### By Formalism

| Doc | Title | Organizing Axis | Examples | Version | Status |
|-----|-------|----------------|----------|---------|--------|
| D1 | From Fresnel to Fock Space | Hamiltonian | 7 (WE-1 through WE-7) | v12 (as C1) | **Complete** |
| D2 | From Action to Amplitude | Path Integral | 7 (PI-WE-1 through PI-WE-7) | v1.0 | **Complete** |

### By Application Domain

| Doc | Title | Domain | Examples | Status |
|-----|-------|--------|----------|--------|
| D3 | Worked Examples in Imaging | Imaging | 6 (3 initial) |  **Complete** |
| D4 | Worked Examples in Illumination | Illumination | 5 (3 initial) | **Complete** |
| D5 | Worked Examples in Sensing | Sensing | 5 (3 initial) | **Complete** |
| D6 | Worked Examples in Communication | Communication | 5 (3 initial) |  **Complete** |

---

## D1 and D2: The Dual-Formalism Pair

D1 and D2 analyze the **same seven physical systems** using two complementary formalisms:

| WE | System | D1 (Hamiltonian) | D2 (Path Integral) | PAL |
|----|--------|-----------------|-------------------|-----|
| 1 | Double Gauss lens (GRIN) | ABCD, symplectic defect | BPM convergence, Maslov index | 2–3 |
| 2 | 50:50 beam splitter | SU(2), HOM dip | Two Feynman diagrams, path cancellation | 1 |
| 3 | Kerr nonlinear medium | Cat-state, Wigner negativity | Two-saddle interference, N_W diagnostic | 3 |
| 4 | Jaynes-Cummings (atom-cavity) | Cooperativity, dressed states | Saddle bifurcation at C_coop = 1 | 3 |
| 5 | Mach-Zehnder interferometer | Strehl = Fidelity, bi-photon Strehl | S = F as propagator ratio, parity immunity | 1–3 |
| 6 | Squeezed state in PhC cavity | Lindblad, ESD | Influence functional, non-Markovian revival | 4 |
| 7 | Stadium billiard | Brody beta (fitted) | Gutzwiller trace formula (predicted beta) | 4 |

**PAL = PI Advantage Level** (0 = Equivalent, 1 = Conceptual, 2 = Corrective, 3 = Complementary, 4 = Transformative). See D2 for full definition and the PAL decision tool.

**Reading guide:** D1 provides energy levels and conservation laws. D2 provides interference patterns and non-local correlations. Together they give the complete picture.

---
---

## Relationship to Other Series

```
Series A (Textbooks-level) ── synthesizes ──► A depends on B
Series B (Pillar Theory)    ── establishes  ──► theoretical foundation
Series C (Toolkits)  ── implements   ──► B as callable code
Series D (Examples)  ── validates    ──► C using B  (this repo)
                     ── calls        ──► C toolkit functions
                     ── reveals gaps ──► feeds back to C
```

- **Engineers** enter at D and pull in C as needed
- **Researchers** enter at B and validate through D
- **Students** enter at A and work downward

---
