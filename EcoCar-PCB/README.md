# STM32 Microcontroller PCB Design — EcoCar

A custom STM32-based printed circuit board (PCB) designed as part of the EcoCar Club electrical team's onboarding project.

The objective was to gain hands-on experience with the PCB development process, from microcontroller configuration and schematic capture to component placement, trace routing, and design verification.

## PCB 3D Model

![PCB 3D Model](images/Onboarding%203D%20model.png)

## Project Overview

The board is built around an **STM32F103C8T6 microcontroller** and incorporates power regulation, USB-C connectivity, communication interfaces, user inputs, and LED indicators.

The design was developed using **KiCad** for schematic capture, PCB layout, and 3D visualization, alongside **STM32CubeMX** for microcontroller pin and peripheral configuration.

### Key Features

- **STM32F103C8T6:** ARM Cortex-M3 microcontroller
- **USB-C:** Connector with USB data and power connections
- **Power regulation:** AMS1117-3.3 regulator for the 3.3 V supply
- **Clock circuitry:** External 16 MHz crystal oscillator
- **Communication:** I²C and UART interfaces brought out to headers
- **User interface:** Push-buttons and LED indicators
- **Expansion:** GPIO breakout headers for external connections
- **Mechanical integration:** Four mounting holes

## Design Process

### 1. Schematic Design

Created the electrical schematic in KiCad, integrating the microcontroller, USB-C connector, voltage regulator, external oscillator, push-buttons, LEDs, and supporting passive components.

Used STM32CubeMX to configure microcontroller pins and peripherals, ensuring that the selected functions were reflected in the schematic.

![KiCad Schematic](images/Onboarding%20schematic.png)

### 2. PCB Layout and Routing

Assigned component footprints and arranged the components to balance electrical connectivity, board space, and accessibility.

Routed PCB traces, placed vias, and configured copper zones to complete the board layout.

During routing, resolved issues involving electrical connectivity, copper clearance, via dimensions, and thermal-relief connections.

![KiCad PCB Layout](images/Onboarding%20PCB%20design.png)

### 3. Design Verification

Performed KiCad's **Electrical Rules Check (ERC)** and **Design Rules Check (DRC)** to identify potential schematic and PCB layout issues.

Iteratively corrected reported errors and warnings until the final design passed both checks with **zero errors and zero warnings**.

### 4. Fabrication and Assembly

The PCB design has been completed and ordered for fabrication through the EcoCar team.

Physical assembly, soldering, hardware bring-up, and functional testing are planned once the fabricated board arrives.

## Tools and Technologies

| Tool | Application |
|---|---|
| KiCad | Schematic capture, PCB layout, routing, ERC/DRC, and 3D visualization |
| STM32CubeMX | Microcontroller pin assignment and peripheral configuration |
| STM32CubeIDE | STM32 embedded development environment |

## Skills Developed

- PCB schematic design and component footprint assignment
- Microcontroller pin and peripheral configuration
- PCB component placement, trace routing, and via placement
- Copper zone configuration and electrical design verification
- Troubleshooting connectivity, clearance, and thermal-relief issues
- Understanding the PCB design-to-fabrication workflow

## Project Status

**PCB design complete — awaiting physical assembly and testing.**

Future work includes soldering the components, verifying power rails, programming the STM32, and testing the board's communication interfaces and input/output functionality.
