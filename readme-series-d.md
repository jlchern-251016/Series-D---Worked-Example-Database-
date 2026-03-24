# Series D — Worked-Example Database

**Author:** Jyh-Long Chern  
**Part of:** [Open-Source Engineering Optics Series](https://github.com/jlchern-251016)  
**Status:** D1 (v12, as C1) and D2 (v1.0) complete; D3–D6 in development

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
| D3 | Worked Examples in Imaging | Imaging | 6 (3 initial) | To be written |
| D4 | Worked Examples in Illumination | Illumination | 5 (3 initial) | To be written |
| D5 | Worked Examples in Sensing | Sensing | 5 (3 initial) | To be written |
| D6 | Worked Examples in Communication | Communication | 5 (3 initial) | To be written |

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

## Seven Standalone Simulation Codes (D2)

Each PI-WE has a standalone Python simulation following the GAI convention:

| PI-WE | Filename | Investigations | Figures |
|-------|----------|---------------|---------|
| 1 | `PI_WE1_GRIN_BPM_Maslov.py` | 5 | 8 |
| 2 | `PI_WE2_BeamSplitter_HOM.py` | 4 | 5 |
| 3 | `PI_WE3_Kerr_CatState.py` | 5 | 7 |
| 4 | `PI_WE4_JC_Grassmann.py` | 4 | 5 |
| 5 | `PI_WE5_MZI_SFidentity.py` | 6 | 10 |
| 6 | `PI_WE6_InfluenceFunctional.py` | 6 | 8 |
| 7 | `PI_WE7_Gutzwiller_Stadium.py` | 6 | 9 |
| | **Total** | **36** | **52** |

All codes: Python 3, NumPy/SciPy/Matplotlib, no QuTiP, CP950-safe, fixed seed 42.

---

## Experimental Validation Summary

| PI-WE | PI Prediction Beyond Hamiltonian | Status |
|-------|--------------------------------|--------|
| 1 | Maslov phase -pi/2 per caustic | **Confirmed** (Gouy phase measurements) |
| 2 | HOM as two-path cancellation | **Confirmed** (Hong-Ou-Mandel, 1987) |
| 3 | N_W as saddle diagnostic | **Partially confirmed** (Wigner tomography of cat states) |
| 4 | C_coop = 1 as saddle bifurcation | **Confirmed** (vacuum Rabi splitting observations) |
| 5 | Bi-photon parity immunity | **Falsifiable prediction** (SiN Sagnac experiment proposed) |
| 6 | Non-Markovian entanglement revival | **Confirmed** (Xu et al., 2010; Hoeppe et al., 2012) |
| 7 | Predictive beta from periodic orbits | **Confirmed** (microwave billiard experiments) |

5 of 7 confirmed; 2 falsifiable predictions on the table.

---

## Relationship to Other Series

```
Series A (Textbooks) ── synthesizes ──► A depends on B
Series B (Theory)    ── establishes  ──► theoretical foundation
Series C (Toolkits)  ── implements   ──► B as callable code
Series D (Examples)  ── validates    ──► C using B  (this repo)
                     ── calls        ──► C toolkit functions
                     ── reveals gaps ──► feeds back to C
```

- **Engineers** enter at D and pull in C as needed
- **Researchers** enter at B and validate through D
- **Students** enter at A and work downward

---

## Repository Structure

```
series-D/
├── D1_Hamiltonian_WE/
│   ├── D1_FromFresnelToFockSpace_v12.pdf
│   └── simulation_codes/
│       ├── we_01_harmonic_oscillator.py
│       ├── ...
│       └── we_07_chaotic_cavity.py
├── D2_PathIntegral_WE/
│   ├── D2_FromActionToAmplitude_v1.pdf
│   ├── D2_scope_v0.md
│   └── simulation_codes/
│       ├── PI_WE1_GRIN_BPM_Maslov.py
│       ├── PI_WE2_BeamSplitter_HOM.py
│       ├── PI_WE3_Kerr_CatState.py
│       ├── PI_WE4_JC_Grassmann.py
│       ├── PI_WE5_MZI_SFidentity.py
│       ├── PI_WE6_InfluenceFunctional.py
│       └── PI_WE7_Gutzwiller_Stadium.py
├── series-summary-v3.md
└── README.md                     # This file
```

---

## Planned Development

| Phase | Timeline | Deliverables |
|-------|----------|-------------|
| Complete | Mar 2026 | D1 (Hamiltonian, 7 WEs), D2 (Path Integral, 7 PI-WEs) |
| Phase 3 | Q4 2026–Q1 2027 | D3 (Imaging: Double Gauss, blind deconvolution, ghost imaging) |
| Phase 4 | Q1–Q3 2027 | D5 (Sensing: MZI phase sensor, NV-diamond, fiber gyroscope) |
| Phase 4 | Q1–Q3 2027 | D4 (Illumination: DMD etendue audit, OAM engineering, uLED) |
| Phase 6 | 2027–2028 | D6 (Communication: OAM MUX, QKD link budget, Si photonic transceiver) |

---

## Citation

```
J.-L. Chern, "Worked-Example Database for Optical Engineering,"
Open-Source Engineering Optics Series, Series D, v1 (2026).
Available: https://github.com/jlchern-251016
```

---

## License

This work is shared for educational and research purposes. Please contact the author for commercial use.

---

*Series D — Worked-Example Database*  
*Author: Jyh-Long Chern*  
*Last updated: March 2026*
