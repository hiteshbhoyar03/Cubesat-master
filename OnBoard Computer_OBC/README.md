#  CubeSat Onboard Computer (OBC)

<p align="center">
<img  width="39%" src="https://github.com/hiteshbhoyar03/Cubesat-master/blob/main/OnBoard%20Computer_OBC/gallery/obc%20front.png">
<img  width="39%" src="https://github.com/hiteshbhoyar03/Cubesat-master/blob/main/OnBoard%20Computer_OBC/gallery/obc%20back.png">
</p>

The Onboard Computer (OBC) is the central control unit of the CubeSat system, designed for low-power operation, robust interfacing, and modular telemetry/command handling. It serves as the core data and control hub, interfacing with sensors and subsystems over multiple buses including SPI, I2C, UART, and CAN.

>  This design emphasizes embedded systems learning, modular subsystem interaction, and reliable firmware development for space applications.

---

##  Functional Block Overview

| Component Type   | Component                       | Function                                  |
|------------------|---------------------------------|-------------------------------------------|
| MCU Core         | STM32L496ZGT6                   | Main application processor                |
| Clock            | NX3225GA (16 MHz)               | High-speed MCU clock                      |
| RTC              | NX3215SA (32.768 kHz)           | Real-time clock for timing and sleep mode |
| Watchdog         | TPL5010Q1                       | System reset if hung                      |
| Inertial         | ISM330ISN                       | Accelerometer + Gyro                      |
| Magnetic         | MMC5983MA                       | 3-axis magnetometer                       |
| MRAM             | MR25H40MDF                      | Non-volatile fast memory                  |
| NOR Flash        | S25HL512TFANHI010               | Bootloader/data storage                   |
| CAN Interface    | TCAN332GDCNT                    | Satellite bus communication               |
| UART Buffer      | SN74LVC2G34DRLR                 | Signal integrity for UART                 |
| USB OTG          | 473460001                       | Micro USB port                            |
| Sun Sensor (x3)  | 503763-0691                     | SPI slave interface                       |
| GPS              | 53261-0771                      | Location services interface               |

---

##  Key Features

- **STM32L496ZGT6**
- **Real-Time Clock & System Clocks**
- **Sensor Suite**
  - `ISM330ISN`: IMU with embedded sensor hub and machine learning core
  - `MMC5983MA`: 3-axis high-precision magnetometer

- **Watchdog Timer**
  - External watchdog for mission resilience and autonomous reset

- **Memory & Storage**
  - MRAM (non-volatile, fast) for telemetry data
  - NOR Flash for data logging and firmware storage

- **Communication Interfaces**
  - CAN transceiver
  - UART  
  - Micro-USB connector for OTG FS (for development/debug)

---

##  External Interfaces

- **Sun Sensor Connectors**
- **GPS Interface**

---


##  Power Considerations

- Powered via EPS board through PC104 connector
- Designed for low power consumption in deep-sleep modes
- All digital IOs are ESD-protected and power-aware

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

##  License

Licensed under the [MIT License](../LICENSE)

---
