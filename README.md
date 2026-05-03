# HW-Glitching-Platform

A custom voltage fault injection platform designed from scratch 
for hardware security research on embedded targets.

Built because real-world attack scenarios don't come with a 
ChipWhisperer connector. This platform is designed to be 
flexible enough to adapt to non-standard targets, the kind 
you encounter in production devices.

## Hardware

**Controller: Digilent CMOD S7 (Spartan-7 FPGA)**
The platform is built around the CMOD S7, chosen because
precise glitch timing at nanosecond resolution requires
deterministic hardware control that a microcontroller cannot
reliably deliver. If you have a CMOD S7, you can use this
platform directly with the provided bitstream and UART API.

## Key Specifications
- 5ns glitch pulse width with precise timing control
  (FPGA-driven — no jitter from software scheduling)
- Variable supply voltage: -5V to +12V (adjustable during attack)
- UART control interface for host-side scripting (API
  open-sourced — see /firmware)
- JTAG/SWD communication interface for target interaction

## What You Need
- Digilent CMOD S7 (Spartan-7)
- Custom PCB (schematic and Gerbers in /hardware — 
  order from JLCPCB or equivalent)
- Component BOM in /hardware/BOM.csv
- Host PC with Python for UART scripting

## Target Research
- Voltage fault injection on 1-Wire and I2C EEPROM
  security devices
- Authentication bypass via instruction skip on ARM
  Cortex-M targets
- Results and attack documentation updated as
  research develops
