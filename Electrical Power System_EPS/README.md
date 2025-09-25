#  CubeSat Electrical Power System (EPS) Board

<p align="center">
<img  width="39%" src="https://github.com/hiteshbhoyar03/Cubesat-master/blob/main/Electrical%20Power%20System_EPS/gallery/EPS_v1%20front.png">
<img  width="39%" src="https://github.com/hiteshbhoyar03/Cubesat-master/blob/main/Electrical%20Power%20System_EPS/gallery/EPS_v1%20back.png">
</p>

This is the dedicated Electrical Power System (EPS) board designed as part of a modular CubeSat architecture. Built around a dual-MCU architecture with power management, overcurrent protection, and solar energy handling, this board ensures regulated and protected power distribution for all CubeSat subsystems.

Designed for reliability, fault tolerance, and modularity, the EPS handles **power generation, regulation, protection, distribution, and monitoring** for the CubeSat stack.

 Built using dual STM32 microcontrollers with redundant control paths and hardware protections, this board aims to simulate a real-world EPS for low-Earth orbit CubeSats.

>  This project is for **learning and portfolio building**, and simulates real-world aerospace-grade embedded systems and power electronics design.

---

##  Learning Objectives

This project is designed to explore:
- Solar MPPT implementation
- Redundancy using dual MCU systems
- CubeSat-style modular hardware stacking
- Embedded peripheral planning (ADC, CAN, Timers, UART)
- Power rail architecture and converter selection
- Fault tolerance via watchdogs and control logic

---

##  Key Features
- Dual **STM32 MCUs**: Power Management + Start - Restart/Reset controller
- **CAN AND UART communication x2**
- **Battery Board interface** (I2C + UART)
- **PC104 interface** for modular stacking
- **Power output status LEDs** for live monitoring
- **Solar MPPT** + current and voltage sensing
- **Watchdogs** and **USB OTG FS** on both MCUs
- **MRAM** for fault logging or telemetry storage

---

##  Dual Microcontroller Architecture
- PMIC | STM32L496  | Power regulation, MPPT, output control           
- SRIC | STM32L452  | Startup, reset, standby and wake-up logic        
- Both MCUs feature:
  - **Watchdog circuits**
  - **USB OTG FS** via Micro-USB connectors
  - 16 MHz crystal and 32.768 kHz RTC crystal 

  ---

##  Battery & Solar Integration
- Battery Board Interface:
  - **I2C + UART** connection
- Solar Power Handling:
  - **MPPT algorithm** implementation
  - **Current sensors** on all 6 panel inputs
  - **Voltage sensors** on:
    -  X+ Panel and Y− Panel Pair
    -  Y+ Panel and Z− Panel Pair
    -  Z+ Panel and X− Panel Pair
  - One **combined Vout panel** monitoring

---

##  Interfaces & Peripherals

| Interface      | Details                                                        |
|----------------|----------------------------------------------------------------|
| **CAN x2**     | CAN for PMIC                                                   |
| **UART**       | Inter-board communication                                      |
| **I2C + UART** | To battery board via dedicated connector                       |
| **ADC (x16)**  | Current sense, Voltage Sense and ntc sensors                   |
| **TIMER (x5)** | Used for battery heater control and MPPT                       |
| **MRAM**       | Non-volatile storage for fault                                 |
| **PC104**      | Standard CubeSat stacking connector for subsystem communication|

---

##  Regulated Outputs

| Name                            | Voltage | Converter            |
|---------------------------------|---------|----------------------|
| `3V3_EPS`,`3V3_SR`,`3V3_MCU_OBC`| 3.3V    | LTC3530              |
| `3V3_1`, `3V3_2`                | 3.3V    | TPS63020Q            |
| `5V_VDD`                        | 5V      | TPS61235             |
| `UNREG_1` , `UNREG_2`           | Raw     | Supplied unregulated |
- All Power outputs are controlled via **OR-gated enable logic** and has Overcurrent protection

---

##  Tools Used

-  **Altium Designer** – Schematic and PCB Layout  
-  **STM32CubeIDE** – Embedded development
-  **STM32CubeMX** – Peripheral and clock config  
-  **GitHub** – VersVersion control , documentation and project showcase

---

##  Author

**Hitesh Bhoyar**  
 Embedded Systems | CubeSat Design | Low Power Electronics  
[GitHub →](https://github.com/hiteshbhoyar03)
> For educational use. Feel free to fork, reuse, or reach out if you are exploring embedded systems!

---

>  Visit the [main repository](https://github.com/hiteshbhoyar03/Cubesat-master) for other subsystems.

---

##  License

Part of the [CubeSat Master Project](https://github.com/hiteshbhoyar03/Cubesat-master)  
Licensed under the [MIT License](../LICENSE)

---
