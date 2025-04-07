# PCB Documentation for Mechanical Arm

## Overview

This document outlines the design, functionality, and integration of the custom PCB developed for the mechanical arm project. The PCB is critical to enabling communication and control at each joint (or node) of the arm via the **CAN bus protocol**.

---

## PCB Design

### 1. 3D Model and Layout

The PCB is designed to be mounted at each node of the mechanical arm. It plays a vital role in receiving commands and controlling the motors at each joint. A **CAN bus** runs across the arm, connecting all nodes and enabling synchronized communication between the microcontrollers.

![3D Model - PCB Mounted on Arm](./Screenshot%202025-04-06%20154113.png)

---

### 2. Key Components on the PCB

- **MCU:** STM32 Blue Pill board for local processing.
- **CAN Transceiver:** Interfaces the MCU with the CAN bus.
- **Buck Converter:** Steps down 24V input to 5V for logic-level operation.
- **Screw Terminals:**
  - **CAN Line Terminal:** For CAN High and CAN Low connections.
  - **Power Line Terminal:** For 24V power input distribution.
- **JST Connectors:**
  - **3-Pin JST:** For motor control signals (GND, PWM, DIR).
  - **5-Pin JST:** For motor encoder signal connections.
- **Limit Switch Connectors:** Two screw terminals for connecting limit switches.
- **Transceiver Header:** Female header for connecting the CAN transceiver module.
- **Male Header Pins:** For UART connection and 2 GPIO pins in reserve.

![Top View - PCB Layout](./Screenshot%202025-04-07%20113859.png)

---

## PCB Integration on the Arm

Each PCB is mounted at an arm node and enclosed in a **3D-printed case** that slides onto the X-rail structure of the mechanical arm. Wiring is routed internally through the X-rails to maintain a clean and protected layout.

At each joint:
- **Power and CAN lines** are tapped from the main trunk between the X-rail and the slip ring (the black cylindrical component).
- The **power line** connects to the PCB and two motor drivers (mounted on the sides of the X-rails).
- The **CAN line** connects to the PCB’s CAN transceiver, allowing it to receive commands from the central controller.

All electronic components are securely mounted on a **custom-designed 3D-printed enclosure** to ensure mechanical stability and ease of maintenance.

---

## License

This project is part of a student research and development initiative. Please contact the project supervisor for reuse permissions.
