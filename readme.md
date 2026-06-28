# Differential Amplifier Simulation using LTspice

## Overview

This repository presents the LTspice implementation and analysis of a CMOS Differential Amplifier. The objective of the project is to study how changes in the tail current and MOSFET aspect ratio (W/L) affect the amplifier's performance. Three different circuit configurations were simulated, and their behavior was compared using AC Analysis, Transient Analysis, and Operating Point Analysis.

---

# Repository Contents

```text
Differential_Amplifier.asc      -> LTspice schematic of the differential amplifier
circuit.png                     -> Screenshot of the circuit schematic

AC_Analysis_70_9.5.png
AC_Analysis_120_9.5.png
AC_Analysis_70_15.png           -> AC Analysis waveforms

Transient_70_9.5.png
Transient_120_9.5.png
Transient_70_15.png             -> Transient Analysis waveforms

CMOS180.txt                     -> CMOS 180 nm MOSFET model file used for simulation

*.raw
*.log                           -> LTspice-generated simulation files (not required for understanding the project)
```

> **Note:** Since the repository contains only a few files, all files have been kept directly in the main directory instead of being organized into separate folders for easier navigation.

---

# File Naming Convention

Waveform files follow the naming format:

```text
<Type>_<Tail Current>_<W/L Ratio>
```

Examples:

* **AC_Analysis_70_9.5**

  * AC Analysis
  * Tail Current = **70 µA**
  * MOSFET W/L = **9.5**

* **Transient_120_9.5**

  * Transient Analysis
  * Tail Current = **120 µA**
  * MOSFET W/L = **9.5**

* **AC_Analysis_70_15**

  * AC Analysis
  * Tail Current = **70 µA**
  * MOSFET W/L = **15**

---


<img width="1868" height="743" alt="Screenshot 2026-06-28 152757" src="https://github.com/user-attachments/assets/7c8a0ddb-f790-417d-b208-9af44d7fb5b9" />
Circuit.png


# Circuit Configurations

Three different operating conditions were analyzed.

## Case 1 (Baseline)

* Tail Current = **70 µA**
* MOSFET W/L = **9.5**

## Case 2

* Tail Current = **120 µA**
* MOSFET W/L = **9.5**

## Case 3

* Tail Current = **70 µA**
* MOSFET W/L = **15**

---

# Simulations Performed

## 1. AC Analysis

AC Analysis was performed to evaluate the frequency response of the amplifier. The following parameters were measured:

* Maximum Voltage Gain
* Initial Phase
* 3 dB Bandwidth

---

## 2. Transient Analysis

Transient Analysis was carried out to observe the amplifier's time-domain response and determine the output voltage amplitude.

---

## 3. Operating Point Analysis

Operating Point Analysis was used to determine the DC bias conditions of the circuit, including:

* Output Voltage
* Gate Current of M1 (Ib)
* Source Current of M1 (Is)

---

# Simulation Results

| Parameter                        | Case 1<br>(70 µA, W/L = 9.5) | Case 2<br>(120 µA, W/L = 9.5) | Case 3<br>(70 µA, W/L = 15) |
| :------------------------------- | :--------------------------: | :---------------------------: | :-------------------------: |
| Maximum Gain                     |         **38.15 dB**         |          **36.93 dB**         |         **38.55 dB**        |
| Initial Phase                    |            **0°**            |             **0°**            |            **0°**           |
| 3 dB Bandwidth                   |         **60.32 MHz**        |         **101.8 MHz**         |        **61.85 MHz**        |
| Output Voltage (Operating Point) |          **1.029 V**         |          **0.916 V**          |         **1.098 V**         |
| M1 Gate Current (Ib)             |      **−1.49 × 10⁻¹² A**     |      **−1.338 × 10⁻¹² A**     |         **−1.58 fA**        |
| M1 Source Current (Is)           |          **−35 µA**          |           **−60 µA**          |          **−35 µA**         |
| Output Voltage Amplitude         |          **1.44 V**          |           **1.38 V**          |         **1.524 V**         |

---

# Observations

## Effect of Increasing Tail Current (70 µA → 120 µA)

* Bandwidth increased significantly from **60.32 MHz** to **101.8 MHz**.
* Voltage gain decreased slightly.
* Operating point output voltage reduced.
* Source current increased due to the higher bias current.
* Output voltage amplitude showed a small decrease.

**Conclusion:** Increasing the tail current improves the amplifier's bandwidth while causing a slight reduction in gain and output amplitude.

---

## Effect of Increasing MOSFET W/L Ratio (9.5 → 15)

* Maximum gain increased slightly.
* Bandwidth remained almost unchanged.
* DC output voltage increased.
* Output voltage amplitude increased.
* Source current remained nearly constant because the tail current was unchanged.

**Conclusion:** Increasing the transistor aspect ratio provides a modest improvement in gain and output swing without significantly affecting the bandwidth.

---

# Key Learning Outcomes

Through this project, the following concepts were explored and verified using LTspice:

* Designed and simulated a CMOS Differential Amplifier.
* Performed AC, Transient, and Operating Point analyses in LTspice.
* Studied the relationship between bias current and amplifier bandwidth.
* Investigated how MOSFET aspect ratio (W/L) influences gain and output characteristics.
* Compared multiple design configurations using quantitative simulation results.
* Gained practical experience in analog circuit analysis, parameter optimization, and interpretation of simulation waveforms.

---

# Software Used

* **LTspice**

---

# Files to Review

If you are viewing this repository for the first time, the recommended order is:

1. `circuit.png` – Circuit schematic
2. `Differential_Amplifier.asc` – LTspice source file
3. `AC_Analysis_*.png` – Frequency response of each configuration
4. `Transient_*.png` – Time-domain response of each configuration
5. Simulation results table in this README

The `.raw` and `.log` files are automatically generated by LTspice and are included only for completeness.

---

# Future Improvements

Possible extensions to this project include:

* Measuring input offset voltage and common-mode rejection ratio (CMRR).
* Evaluating power consumption across different bias conditions.
* Performing noise analysis and stability analysis.
* Comparing simulation results with theoretical hand calculations.

---

## Author
Gaurish Juneja
