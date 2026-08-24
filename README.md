# 🌡️ VTC Design Explorer

> ⚡ **Interactive first-order design tool for low-power Voltage-to-Time Converter (VTC) interfaces used with analog temperature sensors.**

## ✨ What it does

- 🎯 Supports **LMT70/LMT70A**, **TMP236**, and **Custom voltage-output sensors**
- 🌡️ Converts temperature requirements into electrical VTC requirements
- 🔀 Supports **single- and multi-channel** acquisition
- ⚙️ Recommends an initial:
  - `K_VTC`
  - `C_INT`
  - `I_REF`
  - `f_CLK`
  - `f_VTC`
- 📊 Explores **CINT**, **IREF**, and **VTC-rate** trade-offs
- 🗺️ Shows the **CINT–IREF feasibility map**
- ✅ Classifies designs as:
  - Feasible
  - Resolution-limited
  - Conversion-time-limited
  - Leakage-sensitive
- 📤 Exports the recommended specification as **JSON**

---

## 🚀 Quick Start

1. 🎛️ Select the **sensor**
2. 🌡️ Set `T_MIN`, `T_MAX`, and `ΔT_REQ`
3. 🔢 Select the **number of channels**
4. ⚙️ Define limits for `C_INT`, `I_REF`, `f_VTC`, and `f_CLK`
5. ▶️ Click **Calculate & Recommend**
6. ✅ Review the **Recommended Initial VTC Specification**
7. 📈 Explore alternative design points using the sweep plots and feasibility map

---

## 🧭 Design Flow

**Sensor → Thermal Requirements → Voltage Requirement → Channel Count → VTC Limits → Feasibility → Recommended VTC Specification**

---

## 📋 Main Outputs

The explorer reports:

- 🌡️ Sensor and temperature range
- ⚡ Required sensor-voltage increment and VTC input window
- ⏱️ Recommended VTC gain
- 🔋 Recommended integration capacitance and reference current
- 🕒 Recommended VTC clock and conversion rate
- 🎯 Voltage and temperature resolution
- 🔢 Timing counts and counter width
- 🌫️ Capacitor thermal-noise estimate
- 💧 Leakage ratio
- ⚡ First-order ramp-current power contribution

---

## 🔀 Multi-Channel Mode

Supports sequential acquisition from multiple temperature sensors using a shared VTC.

The explorer considers:

- Channel count
- Required per-channel rate
- Aggregate VTC throughput
- MUX switching time
- Analog settling time
- Reset time
- Guard / latch timing

---

## ⚠️ Important

For sensors such as **LMT70**, the absolute output may be around `0.9 V`, while the useful temperature-dependent variation is only a few tens of millivolts.

A narrow VTC input window therefore assumes **input-window translation or differential processing** before the VTC.

---

## 🧪 Design Scope

This tool provides **first-order engineering estimates**.

Before implementation, verify the design using:

- 🔬 Transistor-level simulation
- 📐 PVT analysis
- 🎲 Monte Carlo simulation
- 🧩 Parasitic / extracted simulation
- 🧪 Experimental validation

> ⚠️ The calculated VTC resolution is **not equivalent to clinical temperature accuracy**.

---

## ▶️ Run

Open the HTML file directly in a modern browser:

**Chrome · Edge · Firefox**

No installation is required.

---

## 📌 Version

**VTC Design Explorer — v1.0**

Built for rapid sensor-to-VTC specification and design-space exploration.
