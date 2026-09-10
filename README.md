# 3x3 Macropad with QMK

A custom DIY 3x3 macropad built with a Pro Micro microcontroller running QMK firmware.

## Hardware

- **Microcontroller**: Pro Micro (ATmega32U4)
- **Layout**: 3x3 ortholinear grid (9 keys)
- **Firmware**: QMK (Quantum Mechanical Keyboard)
- **Switches**: Epomaker Wisteria
- **PCB**: Custom designed

## Features

- Fully programmable keys via QMK
- Custom macros and key combinations
- USB connectivity
- Low-latency input
- Open-source firmware
- Automatic keyboard.json file Windows BATCH replacement script
- HTML-based front-end serving as a keyboard.json file creator

## Media

### Videos

<img src="media/macropad/demo-1.gif" alt="Macropad demo 1" width="360" />

<img src="media/macropad/demo-2.gif" alt="Macropad demo 2" width="360" />

### Photos

<img src="media/macropad/assembled.jpeg" alt="Macropad assembled" width="360" />
<img src="media/macropad/angle.jpeg" alt="Macropad angle view" width="360" />

<img src="media/macropad/internals.jpeg" alt="Macropad internals" width="360" />
<img src="media/macropad/build-detail.jpeg" alt="Macropad build detail" width="360" />

<img src="media/macropad/pcb.png" alt="Macropad PCB design" width="360" />
<img src="media/macropad/cad.png" alt="Macropad CAD enclosure" width="360" />

<img src="media/macropad/firmware-ui.png" alt="Macropad firmware UI" width="360" />

## Firmware Setup

### Prerequisites

- QMK MSYS (Windows) or QMK CLI (Mac/Linux)
- Git
- Pro Micro with bootloader

### Installation

1. **Clone QMK firmware repository**
```bash
   git clone --recurse-submodules https://github.com/qmk/qmk_firmware.git
   cd qmk_firmware
