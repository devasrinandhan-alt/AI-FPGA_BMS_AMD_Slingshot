# Battery Management System using Python and Vivado Simulation
### Team CoreX Semiconductors | AMD Slingshot 2026
### Theme: Sustainable AI & Green Tech

---

## About the Project

Battery failures in Energy Storage Systems are a serious problem. When a battery degrades without proper monitoring, it can lead to thermal runaway, unexpected shutdowns, and even fires. Most existing solutions are too slow or too expensive for real-time use.

This project builds a Battery Management System that estimates SOC (State of Charge) and SOH (State of Health) in real time using Python, and simulates the hardware protection logic using Verilog in Xilinx Vivado. The goal is to detect problems before they happen and keep the battery running safely and efficiently.

---

## Problem We Are Solving

- Batteries degrade over time but most systems cannot track this accurately
- Thermal runaway is dangerous and happens when temperature rises too fast
- Existing BMS solutions are slow and do not give real-time predictions
- There is no affordable system that combines software prediction with hardware protection

---

## What Our System Does

- Estimates how much charge is left in the battery (SOC %)
- Estimates how healthy the battery is overall (SOH %)
- Detects dangerous temperature rise and triggers emergency cutoff
- Balances charge across battery cells
- Simulates hardware protection logic in Vivado using Verilog

---

## Technology Stack

| Layer | Tools Used |
|-------|-----------|
| Data Processing | Python, NumPy, Pandas |
| Visualization | Matplotlib |
| SOC and SOH Estimation | Python (Coulomb Counting method) |
| Dataset | NASA Battery Dataset |
| Hardware Simulation | Verilog HDL, Xilinx Vivado |
| Output | Terminal Dashboard, Graphs |

---

## Project Flow

| Step | What Happens |
|------|-------------|
| 1 | NASA battery dataset is loaded into Python |
| 2 | Voltage, current and temperature data is read and cleaned |
| 3 | SOC is calculated using Coulomb Counting method |
| 4 | SOH is estimated by comparing current capacity to original |
| 5 | Temperature data is monitored for thermal runaway detection |
| 6 | Alerts are triggered if temperature rises too fast |
| 7 | Results are displayed as graphs and a live BMS status dashboard |
| 8 | Hardware protection logic is simulated separately in Vivado using Verilog |

---

## Hardware Simulation Modules (Vivado)

| Module | Purpose |
|--------|---------|
| adc_interface.v | Reads voltage and temperature input |
| thermal_monitor.v | Detects dangerous temperature rise |
| cell_balancer.v | Balances charge between cells |
| alert_controller.v | Triggers protection based on sensor data |
| uart_tx.v | Sends output data to dashboard |

---

## AMD Tools Used

| Tool | How We Use It |
|------|--------------|
| Xilinx Vivado Design Suite | Simulate and verify Verilog BMS modules |
| Vivado IP Catalog | UART and BRAM cores for hardware design |
| AMD Xilinx FPGA (Artix-7) | Target platform for future hardware deployment |

---

## How to Run the Python Demo

**Step 1 — Install required libraries**
```
pip install numpy pandas matplotlib scikit-learn
```

**Step 2 — Download NASA Battery Dataset**

Go to: https://data.nasa.gov/dataset/Li-ion-Battery-Aging-Datasets

Download B0005.csv and place it in the same folder as battery_analysis.py

**Step 3 — Run the script**
```
python battery_analysis.py
```

**Step 4 — View the output**

You will see SOC and SOH graphs, temperature alerts, and a live BMS status dashboard in the terminal.

---

## Team

| Name | Role |
|------|------|
| Shashank Ganji | Team Leader — Python Development and BMS Logic |
| Bacchu Manikanta | Verilog Design and Vivado Simulation |
| Deva Sri Nandan | Research, Documentation and Presentation |

**Hackathon:** AMD Slingshot 2026
**Platform:** Hack2Skill (H2S)

---

## Dataset Credit

NASA Battery Dataset — NASA Ames Prognostics Center of Excellence
https://data.nasa.gov/dataset/Li-ion-Battery-Aging-Datasets
