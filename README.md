# three-stage-ota-with-nested-miller-compensation
A fully characterized 90dB, 6.33MHz three-stage CMOS OTA with nested-Miller compensation, Monte Carlo, PSRR, noise, and temperature analysis. Designed in LTspice using 0.35µm BSIM3v3 models

# Three-Stage CMOS Operational Transconductance Amplifier (OTA)

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Made with LTspice](https://img.shields.io/badge/Made%20with-LTspice-blue.svg)](https://www.analog.com/en/design-center/design-tools-and-calculators/ltspice-simulator.html)
[![CMOS](https://img.shields.io/badge/Technology-0.35%C2%B5m%20CMOS-green.svg)]()

**A fully characterized, robust three-stage OTA designed in a 0.35 µm CMOS process.**

---

## 🎯 Overview

This project presents a three-stage CMOS OTA using **nested-Miller compensation** with a nulling resistor to achieve high gain and stability. The design was implemented in **LTspice** using **BSIM3v3 (Level 49) models** for a 0.35 µm process.

The amplifier achieves **90 dB DC gain**, **6.33 MHz unity-gain bandwidth**, and **49.91° phase margin** with a **10 pF load**.

---

## 📊 Key Specifications

| **Parameter** | **Value** | **Condition** |
|:---|:---|:---|
| **Technology** | 0.35 µm CMOS | AMS Process |
| **Supply Voltage** | ±1.5 V (3 V total) | - |
| **DC Gain** | 90 dB | @ 10 Hz |
| **Unity-Gain Bandwidth (GBW)** | 6.33 MHz | 10 pF Load |
| **Phase Margin** | 49.91° | - |
| **Slew Rate** | 3 V/µs | ±200 mV Step |
| **Input-Referred Noise** | 7.74 nV/√Hz | @ 1 kHz |
| **PSRR** | 30.86 dB | @ 31.5 kHz |
| **Power Dissipation** | ~1.5 mW | 500 µA Total |
| **Monte Carlo (Worst PM)** | 41.41° | 100 Iterations |
| **Temperature Range** | -40°C to 85°C | Gain: 76.97 dB @ 85°C |

---

## 🧪 Simulation Results

| **Analysis** | **Result** | **Status** |
|:---|:---|:---|
| **DC Gain & Phase Margin** | 90 dB, 49.91° | ✅ Stable |
| **PSRR** | 30.86 dB @ 31.5 kHz | ✅ Good |
| **Input Noise** | 7.74 nV/√Hz @ 1 kHz | ✅ Exceptional |
| **Monte Carlo** | Worst PM: 43.23° | ✅ Robust |
| **Temperature Sweep** | 76.97 dB, 30° PM @ 85°C | ⚠️ Marginal at High Temp |
| **Slew Rate** | 3 V/µs | ✅ Good |

---

## 🧠 Design Methodology

### Compensation Strategy
Nested-Miller compensation was used to stabilize the three-stage amplifier. After initial instability (negative phase margin), the compensation caps were increased to **30 pF each**, achieving **49.91° phase margin**.

### Monte Carlo Analysis
100 iterations were performed to validate robustness. The worst-case phase margin was **43.23°**, confirming the design's resilience to process variations.

### Temperature Sweep
The amplifier was characterized from -40°C to 85°C. At 85°C, the gain drops to 76.97 dB and the phase margin to 30°, indicating a need for temperature compensation in high-temperature applications.

---

## 🔧 How to Run the Simulation

### Prerequisites
- LTspice (Version 26 or later)
- BSIM3v3 model files (included in the `/simulations/models` folder)

### Steps
1. Clone this repository.
2. Open `simulations/netlists/ota_class_a.net` in LTspice.
3. Run the simulation.
4. Plot the following traces:
   - AC Analysis: `V(vout)` and `ph(V(vout))`
   - Noise: `V(inoise)`
   - Transient: `V(vout)`

---

## 📁 Repository Structure

```
📁 three-stage-ota-with-nested-miller-compensation
├── 📁 docs
│   └── 📄 Draft3.asc
│   └── 📄 Draft3.log
│   └── 📄 Draft3.op.raw
│   └── 📄 Draft3.raw
│   └── 📄 schematic.png           # Circuit schematic
├── 📁 sims
│   ├── 📁 netlists                # LTspice netlist files
│   │   └── 📄 netlist.net
│   ├── 📁 plots                   # Simulation plots (PNG/PDF)
│   │   ├── 📄 ac_analysis.png
│   │   ├── 📄 monte_carlo_dcgain_variation.png
│   │   ├── 📄 monte_carlo_line_plot.png
│   │   ├── 📄 noise_analysis.png
│   │   ├── 📄 opta.txt
│   │   ├── 📄 phase_margin.png
│   │   └── 📄 psrr.png
│   │   └── 📄 slew_rate_analysis.png
│   │   └── 📄 temperature_analysis.png
│   └── 📁 models                  # BSIM3v3 model files
│       └── 📄 p35_models_tt.inc
│       └── 📄 p35_models_ttm.inc
├── 📄 README.md                   # This file
└── 📄 LICENSE                     # MIT License
```

---

## 📚 References

- Cannizzaro, S. O., Grasso, A. D., Mita, R., Palumbo, G., & Pennisi, S. (2007). *"Design Procedures for Three-Stage CMOS OTAs With Nested-Miller Compensation."* IEEE Transactions on Circuits and Systems I: Regular Papers, 54(5), 933-940.

---

## 📝 Author

Anirudh Sundarajan 
BTech in Electronics and Communication Engineering, VIT Chennai  
(https://www.linkedin.com/in/anirudh-sundarajan/ )

---

## 🏷️ Tags

`#AnalogICDesign` `#CMOS` `#OTA` `#VLSI` `#Semiconductors` `#CircuitDesign`

---

## ⚠️ Disclaimer

This project was designed for educational purposes. The models used are for simulation only and are not intended for fabrication.

---

## 🚀 Future Work

- Implement a **temperature-compensated bias circuit** (e.g., bandgap reference) to improve high-temperature performance.
- Design a **fully differential** version with common-mode feedback.
- Perform **layout** and post-layout extraction.

---

**Feel free to reach out if you have any questions or suggestions!**
