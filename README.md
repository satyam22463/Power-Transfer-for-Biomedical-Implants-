# Analysis of Resonant and Non-Resonant Wireless Power Transfer Systems for Biomedical Implants

[cite_start]This repository contains the LTSpice models, simulation data, parametric sweep scripts, and experimental datasets for a 5 MHz wireless power transfer (WPT) system designed for biomedical implants[cite: 5]. [cite_start]The project evaluates both 2-coil and 3-coil topologies under resonant and non-resonant conditions to optimize power transfer efficiency (PTE) over varying separation distances[cite: 6, 7].

---

## 👥 Authors & Contributions
[cite_start]The project was developed by the following team members at the Department of Electronics and Communication Engineering, IIIT-Delhi[cite: 2, 3, 4]:

* [cite_start]**Tejaswi**: Developed the LTSpice models for both the resonant and non-resonant 2-coil WPT systems[cite: 142].
* [cite_start]**Satyam**: Developed the LTSpice model for the non-resonant 3-coil WPT system and fabricated the experimental coils[cite: 143].
* [cite_start]**Anirudh**: Developed the resonant 3-coil LTSpice model, implemented the Python script for the parametric distance study, and co-prepared the technical documentation[cite: 144].
* [cite_start]**Team Contribution**: All members collectively participated in the VNA-based experimental validation, laboratory setup, and data collection[cite: 145].

---

## 🛠️ System Specifications

### 1. Coil Hardware & Design
* [cite_start]**Coil Typology**: Two planar spiral coil families (Coil A: smaller, higher-inductance; Coil B: larger, lower-inductance)[cite: 27, 28].
* [cite_start]**Material**: 20 AWG copper wire[cite: 29].
* [cite_start]**Turn Spacing**: 1 mm[cite: 29].
* [cite_start]**System Impedance**: Both source and load resistances are fixed at 50 Ω[cite: 30].

### 2. Electrical Configuration
* [cite_start]**Operating Frequency**: 5 MHz[cite: 5].
* [cite_start]**Resonant Compensation**: Selected series tuning capacitors to match the 5 MHz operating frequency[cite: 31].
* **Simulation Coupling Coefficients ($k$)**: 
  * [cite_start]Source-to-relay link: $k = 0.01$[cite: 36].
  * [cite_start]Relay-to-load link: $k = 0.3$[cite: 36].

---

## 📊 Summary of Key Findings

1. [cite_start]**Resonant vs. Non-Resonant**: Resonant tuning drastically improves transfer efficiency over non-resonant operations, which remain highly inefficient across the entire 2 MHz to 8 MHz frequency sweep[cite: 8, 62, 65].
2. [cite_start]**3-Coil vs. 2-Coil Topologies**: The 3-coil resonant system incorporates an intermediate relay coil that enhances magnetic coupling and provides a significantly higher tolerance to coil separation distance (0 mm to 40 mm) compared to the 2-coil configuration[cite: 9, 32, 39].
3. [cite_start]**Simulation vs. Experimental Discrepancies**: While the physical VNA measurement matched the downward trend predicted by simulations, the real-world efficiencies were drastically lower (e.g., 1.33% measured vs. ~40-50% simulated at 10 mm)[cite: 101, 102]. [cite_start]This is due to practical non-ideal factors like copper ohmic losses, skin/proximity effects at 5 MHz, parasitic capacitances, coil alignment errors, and VNA cable losses[cite: 105, 106, 107].

---

## 📋 Gathered Laboratory Data

[cite_start]The following data table represents the physically validated measurements of the resonant 2-coil WPT system gathered using a Vector Network Analyzer (VNA)[cite: 113]:

| [cite_start]Distance (mm) [cite: 114] | [cite_start]Measured $S_{21}$ (dB) [cite: 114] | [cite_start]Calculated Efficiency (%) [cite: 114] |
| :--- | :--- | :--- |
| [cite_start]10 [cite: 114] | [cite_start]-18.75 [cite: 114] | [cite_start]1.33% [cite: 114] |
| [cite_start]20 [cite: 114] | [cite_start]-23.6 [cite: 114]  | [cite_start]0.44% [cite: 114] |
| [cite_start]30 [cite: 114] | [cite_start]-28.4 [cite: 114]  | [cite_start]0.14% [cite: 114] |
| [cite_start]40 [cite: 114] | [cite_start]-31.03 [cite: 114] | [cite_start]0.079% [cite: 114] |

[cite_start]Efficiency calculation derived from the transmission parameter formula[cite: 42]:
$$\eta \approx 10^{(S_{21}/10)} \times 100\%$$

---

    └── vna_measurements.csv        # Tabulated experimental validation data
