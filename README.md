# 2.45 GHz Half-Wave Dipole Antenna (CST Studio)

**Author:** Edgar Bautista  
**Tools:** CST Studio Suite, MATLAB  
**Category:** RF Antenna Design → Simulation → Measurement Ready  
**Objective:** Design, simulate, and characterize a 2.45 GHz half-wave dipole antenna for ISM/Wi-Fi band applications.

---

## 📡 Project Summary

This project implements a **2.45 GHz half-wave dipole antenna** in CST Studio Suite and validates its performance through full-wave simulation and post-processing in MATLAB.

The design follows antenna theory principles from
Balanis, *Antenna Theory: Analysis and Design*, and targets practical RF deliverables:

- Return Loss: **< −10 dB** at 2.45 GHz
- −10 dB Bandwidth: **≥ 80 MHz**
- Realized Gain: **≈ 2 dBi**
- Radiation Pattern: **Doughnut, broadside maximum**
- Feed: **50 Ω lumped port**

This project forms the foundation for future work in:
- Printed dipoles & baluns,
- Wi-Fi/LoRa antenna design,
- Dipole arrays & beam steering,
- SDR hardware-in-the-loop (PlutoSDR).

---

## 🧠 Design Theory

| Parameter | Value |
|---|---|
Center Frequency | 2.45 GHz |
Wavelength λ | 122.45 mm |
Ideal half-wave | 61.23 mm |
Practical factor | 0.95 (end effect) |
Final length (`L_total`) | ~58 mm |
Arm length | ~29 mm each |
Conductor diameter | 2.0–3.0 mm |
Feed gap | 1.0 mm |
Target input Z | ~73 Ω |

> **Goal:** Minimize |S11| at 2.45 GHz while maintaining typical dipole radiation shape and efficiency.

Full theory notes in: `design_notes/dipole_2p45GHz_theory.md`

---

## 🏗️ CST Build Configuration

- **Geometry:** Two copper arms, centered, 1 mm feed gap
- **Port:** Discrete Port, 50 Ω
- **Boundary:** Open (add space), ≥ λ/4
- **Mesh:** Adaptive refinement at feed
- **Frequency Sweep:** 2.20 – 2.70 GHz

Key tunable parameters:
- Total length (`L_total`)
- Wire diameter (`wire_d`)

---

## 📊 Results Summary *(placeholder values)*

| Metric | Target | Result |
|---|---|---|
Resonant freq | 2.45 GHz | **2.45 GHz** ✅ |
S11 @ f₀ | ≤ −10 dB | **−XX.X dB** |
−10 dB BW | ≥ 80 MHz | **XXX MHz** |
Realized Gain | ~2 dBi | **X.XX dBi** |
Efficiency | — | **XX%** |
Final length | ~58 mm | **XX.X mm** |

> Replace placeholders after CST run.

---

## 📈 Plots

Add these here after export:

- `S11_plot.png`
- `smith_plot.png`
- `pattern_3D_2p45GHz.png`

---

## 🧪 Measurement-Ready Workflow

Once lab access is granted:

| Step | Task |
|---|---|
1 | Calibrate NanoVNA at antenna feed point (SOL) |
2 | Sweep 2.2–2.7 GHz |
3 | Tune length in 0.5–1.0 mm steps |
4 | Compare Sim vs Meas: S11, BW, f₀ |

NanoVNA checklist stored in `measurement/`.

---

## 🚀 Future Extensions

- Folded dipole & **4:1 balun**
- 2-element array w/ mutual coupling study
- PlutoSDR spectrum capture
- Add enclosure/detuning study
- RF matching network co-design (ADS)

---

## 📂 Repository Structure

