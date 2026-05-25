# STM32

Compact STM32F103C8T6 controller board designed in KiCad, with USB power and native USB data lines broken out on PA11/PA12. The design includes on-board 3.3 V regulation, external 16 MHz crystal, filtered analog supply (VDDA), BOOT0 selection, and headers for SWD, UART1, and I2C2. Use it as a reference design or a starting point for custom STM32 hardware.

## Highlights

- Complete KiCad project: schematic, PCB, and project files
- Manufacturing-ready outputs (Gerbers, drill files, and pick-and-place)
- 3D model included for enclosure fit checks

## Preview

### 3D View

![3D View](3D%20View.png)

### PCB Layout

![PCB Layout](PCB%20Layout.png)

### PCB Schematic

![PCB Schematic](PCB%20Schematic.png)

## What is in this repo

- KiCad source files: schematic, PCB, and project settings
- Mechanical model: STEP file for enclosure alignment
- Manufacturing outputs: Gerbers, drill file, and component placement CSVs
- Reference renders: 3D view, layout, and schematic images

## File labels

| File | Label |
| --- | --- |
| [STM32.kicad_sch](STM32.kicad_sch) | Schematic source |
| [STM32.kicad_pcb](STM32.kicad_pcb) | PCB layout source |
| [STM32.kicad_pro](STM32.kicad_pro) | KiCad project settings |
| [STM32.kicad_prl](STM32.kicad_prl) | KiCad local settings |
| [629105150521 (rev1).stp](629105150521%20(rev1).stp) | 3D mechanical model |
| [3D View.png](3D%20View.png) | 3D render |
| [PCB Layout.png](PCB%20Layout.png) | PCB layout render |
| [PCB Schematic.png](PCB%20Schematic.png) | Schematic render |
| [Manufacturing/STM32.csv](Manufacturing/STM32.csv) | Component list export |
| [Manufacturing/STM32-all-pos.csv](Manufacturing/STM32-all-pos.csv) | Pick-and-place positions |
| [Manufacturing/Gerber/](Manufacturing/Gerber/) | Gerber and drill outputs |
| [README.md](README.md) | Project overview |

## Hardware overview

- Power: USB VBUS into AMS1117-3.3 with bulk input/output caps and a power LED
- Clocking: 16 MHz crystal with load capacitors on HSE
- Boot/reset: BOOT0 SPDT switch, pull resistor, and NRST capacitor
- USB: D+ and D- on PA12/PA11 with 1.5 k pull-up on D+
- Debug: 1x4 SWD header (3.3 V, SWDIO, SWCLK, GND)
- IO headers: UART1 and I2C2 (with pull-ups) on 1x4 headers
- Mechanical: four M2 mounting holes

## Bill of materials (BOM)

Values are taken from the schematic. Confirm footprints and ratings before ordering.

| Ref(s) | Qty | Value / Part | Notes |
| --- | --- | --- | --- |
| U2 | 1 | STM32F103C8T6 | LQFP-48 MCU |
| U1 | 1 | AMS1117-3.3 | 5 V to 3.3 V LDO |
| Y1 | 1 | 16 MHz crystal | HSE clock |
| C1, C2 | 2 | 22 uF | LDO input/output bulk |
| C3 | 1 | 10 uF | VDD bulk |
| C4, C5, C6, C7 | 4 | 100 nF | VDD decoupling (one per VDD pin) |
| C8 | 1 | 10 nF | VDDA filter |
| C9, C10 | 2 | 1 uF | VDDA filtering |
| C11 | 1 | 100 nF | NRST cap |
| C12, C13 | 2 | 10 pF | Crystal load caps |
| FB1 | 1 | Ferrite bead, 120 R | VDDA filter |
| D1 | 1 | Red LED | Power indicator |
| R1 | 1 | 1.5 k | LED series resistor |
| R2 | 1 | 10 k | BOOT0 pull |
| R3 | 1 | 1.5 k | USB D+ pull-up |
| R4, R5 | 2 | 1.5 k | I2C pull-ups |
| SW1 | 1 | SPDT switch | BOOT0 select |
| J1 | 1 | Micro-USB B receptacle | USB + power |
| J2 | 1 | 1x4 header | UART1 header |
| J3 | 1 | 1x4 header | SWD header |
| J4 | 1 | 1x4 header | I2C2 header |
| H1, H2, H3, H4 | 4 | M2 mounting holes | Mechanical |


