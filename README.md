# Analysis of Resonant and Non-Resonant Wireless Power Transfer Systems for Biomedical Implants

This repository contains the LTSpice models, simulation data, parametric sweep scripts, and experimental datasets for a 5 MHz wireless power transfer (WPT) system designed for biomedical implants. The project evaluates both 2-coil and 3-coil topologies under resonant and non-resonant conditions to optimize power transfer efficiency (PTE) over varying separation distances.

---

## 👥 Authors & Contributions
The project was developed by the following team members at the Department of Electronics and Communication Engineering, IIIT-Delhi:

* **Tejaswi**: Developed the LTSpice models for both the resonant and non-resonant 2-coil WPT systems.
* **Satyam**: Developed the LTSpice model for the non-resonant 3-coil WPT system and fabricated the experimental coils.
* **Anirudh**: Developed the resonant 3-coil LTSpice model, implemented the Python script for the parametric distance study, and co-prepared the technical documentation.
* **Team Contribution**: All members collectively participated in the VNA-based experimental validation, laboratory setup, and data collection.

---

## 🛠️ System Specifications

### 1. Coil Hardware & Design
* **Coil Typology**: Two planar spiral coil families (Coil A: smaller, higher-inductance; Coil B: larger, lower-inductance).
* **Material**: 20 AWG copper wire.
* **Turn Spacing**: 1 mm.
* **System Impedance**: Both source and load resistances are fixed at 50 Ω.

### 2. Electrical Configuration
* **Operating Frequency**: 5 MHz.
* **Resonant Compensation**: Selected series tuning capacitors to match the 5 MHz operating frequency.
* **Simulation Coupling Coefficients ($k$)**: 
  * Source-to-relay link: $k = 0.01$.
  * Relay-to-load link: $k = 0.3$.

---

## 📊 Summary of Key Findings

1. **Resonant vs. Non-Resonant**: Resonant tuning drastically improves transfer efficiency over non-resonant operations, which remain highly inefficient across the entire 2 MHz to 8 MHz frequency sweep.
2. **3-Coil vs. 2-Coil Topologies**: The 3-coil resonant system incorporates an intermediate relay coil that enhances magnetic coupling and provides a significantly higher tolerance to coil separation distance (0 mm to 40 mm) compared to the 2-coil configuration.
3. **Simulation vs. Experimental Discrepancies**: While the physical VNA measurement matched the downward trend predicted by simulations, the real-world efficiencies were drastically lower (e.g., 1.33% measured vs. ~40-50% simulated at 10 mm). This is due to practical non-ideal factors like copper ohmic losses, skin/proximity effects at 5 MHz, parasitic capacitances, coil alignment errors, and VNA cable losses.

---

## 📋 Gathered Laboratory Data

The following data table represents the physically validated measurements of the resonant 2-coil WPT system gathered using a Vector Network Analyzer (VNA):

| Distance (mm) | Measured $S_{21}$ (dB) | Calculated Efficiency (%) |
| :--- | :--- | :--- |
| 10 | -18.75 | 1.33% |
| 20 | -23.6  | 0.44% |
| 30 | -28.4  | 0.14% |
| 40 | -31.03 | 0.079% |

Efficiency calculation derived from the transmission parameter formula:
$$\eta \approx 10^{(S_{21}/10)} \times 100\%$$

---
├── simulation/                     # LTSpice Schematic files (.asc)
│   ├── 2-coil/
│   │   ├──
