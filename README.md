# ESP32 Programmable PWM Controller with Modbus RTU

This project is a custom-designed ESP32-based programmable controller PCB.  
The board is designed to generate multiple PWM output signals and communicate with a master controller using **Modbus RTU over RS-485**.

This PCB was designed as part of my automation and grow-light control development work, where reliable PWM control and wired communication are required.

---

## PCBWay Sponsorship

This PCB project was sponsored by **PCBWay**.

Special thanks to **PCBWay** for supporting the fabrication of this PCB and helping me turn the design into a real working hardware prototype. Their support helped me test the schematic, PCB layout, power supply section, ESP32 controller section, PWM outputs, and Modbus RTU communication interface on an actual manufactured board.

---

## Project Overview

The board is built around the **ESP32-WROOM-32D** module.  
It can be programmed to generate PWM signals for external driver circuits such as LED drivers, MOSFET drivers, fan controllers, or other automation circuits.

The board also includes a **MAX485 RS-485 transceiver**, allowing it to communicate using Modbus RTU. This makes the board suitable for multi-node automation systems where one master controller communicates with multiple slave devices.

---

## Main Features

- ESP32-WROOM-32D based controller
- Multiple programmable PWM output channels
- MAX485 RS-485 transceiver for Modbus RTU communication
- RS-485 A/B communication connector
- UART programming connector with DTR and RTS support
- 12 V power input
- 12 V to 5 V buck converter section
- 5 V to 3.3 V regulator section
- Reset / EN push button
- Status LED
- 2-layer PCB design
- Designed using KiCad
- Suitable for automation, lighting control, and grow-light control applications

---

## Hardware Sections

### 1. ESP32 Controller Section

The ESP32-WROOM-32D is the main controller of the board.

It is responsible for:

- Generating PWM signals
- Handling Modbus RTU communication
- Controlling RS-485 transmit and receive direction
- Managing output channel states
- Running the main firmware logic

The ESP32 also provides enough flexibility for future firmware upgrades such as sensor reading, status monitoring, and dashboard communication.

---

### 2. PWM Output Section

The board includes multiple PWM output headers.  
These outputs are ESP32 logic-level signals and can be used to control external driver circuits.

Example uses:

- LED dimming control
- Grow-light channel control
- Fan speed control
- MOSFET driver input control
- Relay or actuator driver control
- General automation output control

> Important: The PWM outputs should not be used to directly drive high-power loads.  
> Use a suitable external driver circuit such as a MOSFET driver, relay driver, or constant-current LED driver.

---

### 3. Modbus RTU / RS-485 Section

The board uses a MAX485 transceiver for RS-485 communication.

This section includes:

- MAX485 IC
- A and B differential RS-485 bus lines
- DI, RO, DE, and RE control signals
- RS-485 connector
- Biasing resistor network
- Optional termination resistor support

The RS-485 interface allows the board to work as a Modbus RTU slave device in a wired automation network.

---

### 4. Power Supply Section

The board is powered from a 12 V input supply.

The power section includes:

- 12 V input connector
- Input protection diode
- LM2596S-5.0 buck converter for 5 V generation
- AMS1117-3.3 regulator for 3.3 V generation
- Input and output filtering capacitors

Power flow:

```text
12 V Input
   |
   |-- LM2596S-5.0 Buck Converter
   |
  5 V Rail
   |
   |-- AMS1117-3.3 Regulator
   |
  3.3 V Rail
   |
 ESP32 + Logic Circuit
 Master Controller
       |
       | Modbus RTU over RS-485
       |
 ESP32 Programmable PWM Controller
       |
       | PWM Outputs
       |
 External LED / MOSFET / Driver Circuits
       |
 Grow Light Channels / Fans / Actuators


<p align="center">
  <img src="assests\3.PNG" width="620"/>
</p>



-
## 🙏 Thanks to PCBWay

<img src="assets\dd.jpg" alt="PCBWay Sponsored PCB" width="600">

All of the design work on this **ESP32 Programmable PWM Controller with Modbus RTU** — concept, schematic design, PCB routing, firmware development, and debugging — is self-driven.

This board was designed as a compact embedded controller that can generate multiple PWM outputs and communicate through **Modbus RTU using the MAX485 RS-485 transceiver**. It includes the ESP32 controller section, power regulation section, programming interface, RS-485 communication section, and external PWM output headers.

Manufacturing a reliable 2-layer PCB with an ESP32 module, switching power supply section, RS-485 communication lines, and multiple I/O headers requires a good PCB fabrication partner.

For this project, **PCBWay** supported the PCB fabrication, which helped me turn the KiCad design into a real hardware prototype.

PCBWay’s fabrication service provided:

- Clean soldermask and silkscreen quality
- Accurate drilling for headers, mounting holes, and connectors
- Reliable via quality for the 2-layer PCB routing
- Good copper finish for power and signal traces
- Professional PCB manufacturing quality suitable for testing and debugging
- Fast turnaround, which is very helpful for student and research-based hardware development

A huge thank you to **PCBWay** for supporting this project and helping bring this programmable controller PCB from a design file into a real working board. 🧡

---