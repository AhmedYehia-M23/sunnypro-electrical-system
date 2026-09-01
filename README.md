# SunnyPro - Electrical Architecture & Schematic Design

**STM32H743 · KiCad · hierarchical schematics · sensing · heating · motion control · protected multi-rail power**

Electrical architecture and KiCad schematic design for an automated food-service machine developed as an HSRW group project. My scope was the **electrical architecture and the electrical schematics published in this repository**: MCU I/O planning, power distribution, temperature measurement, heater control, motor/encoder interfaces, load-cell measurement, actuator drivers and component selection.

| | |
|---|---|
| **Controller** | STM32H743 |
| **Architecture** | 8-sheet hierarchical KiCad design |
| **Power rails** | 24 V · 12 V · 6 V · 5 V · 3.3 V |
| **Sensing** | PT100/MAX31865 · HX711 load cell · IR sensors · home switches |
| **Actuation** | SSR heaters · TB6600/NEMA17 · ULN2003A/28BYJ-48 · MOSFET solenoids/pumps · servo |
| **Academic context** | HSRW Group Project · Summer Semester 2026 |

![SunnyPro electrical architecture](images/architecture.svg)

### Quick links

- [Full schematic PDF](exports/SunnyPro-schematics.pdf)
- [KiCad source](hardware/)
- [Design summary](docs/design-summary.md)
- [Power architecture notes](docs/power-architecture.md)
- [Key component selection](docs/key-components.md)
- [Contribution statement](SOURCE_OWNERSHIP.md)

> SunnyPro was a university group project. This repository covers my electrical-design contribution; it does not claim authorship of the team's mechanical or software work.

## Electrical design scope

The electrical work published here includes:

- hierarchical system architecture
- MCU I/O planning and signal allocation
- protected AC input and DC rail architecture
- temperature-sensing and heater-control interfaces
- motor, encoder and home-sensor interfaces
- load-cell measurement interface
- MOSFET-switched actuator channels
- component selection and subsystem interfacing

The original working calculation sheets and purchasing BOM used during project development are not part of this public portfolio release. The repository therefore does not present reconstructed numbers as if they were original project records.

## Design structure

The system is organized into hierarchical KiCad sheets covering:

- MCU and signal interfaces
- AC input protection and DC power distribution
- bottom and top heating systems
- conveyor transportation
- storage and egg-breaking actuators
- rotating plate and load-cell measurement
- oil-pump and HMI/peripheral interfaces

## Temperature measurement and heater control

PT100 RTDs are interfaced through **MAX31865** devices for temperature acquisition. Heater control uses solid-state relays with the protection and low-voltage control interfaces shown in the schematic set.

## Power architecture

The published power design uses a protected mains input and a **Mean Well IRM-60-24** isolated supply as the main 24 V DC source. The system then distributes 24 V, 12 V, 6 V, 5 V and 3.3 V rails according to subsystem requirements.

The rail structure and published protection approach are summarized in [`docs/power-architecture.md`](docs/power-architecture.md).

## Motion, sensors and actuators

The design integrates:

- NEMA17 stepper motor with **TB6600** driver
- step/direction/enable control and encoder feedback
- 28BYJ-48 stepper with **ULN2003A** driver
- **load cell + HX711** measurement interface
- IR sensors and home switches
- MOSFET-switched solenoid and pump channels with flyback protection
- servo actuation
- serial HMI interface

A compact component overview is available in [`docs/key-components.md`](docs/key-components.md).

## MCU integration

The **STM32H743** is the central interface between sensing, motion, heating and HMI subsystems. The schematic set documents the signal allocation and electrical interfaces between those subsystems.

## Project files

```text
hardware/
├── SunnyPro.kicad_pro
├── SunnyPro.kicad_sch
├── SunnyPro.kicad_sym
├── MCU.kicad_sch
├── POWER.kicad_sch
├── CONVEYOR_TRANSPORTATION_SUBSYSTEM.kicad_sch
├── EGG_BREAKING_STORAGE.kicad_sch
├── BOTTOM_HEATING_SUBSYSTEM.kicad_sch
├── TOP_IR_HEATING_SUBSYSTEM.kicad_sch
├── ROTATING_PLATE.kicad_sch
└── PERIPHERALS.kicad_sch

exports/
└── SunnyPro-schematics.pdf

docs/
├── design-summary.md
├── power-architecture.md
└── key-components.md

images/
└── architecture.svg
```

The portfolio scope is **electrical architecture and schematic design**; no SunnyPro PCB-layout authorship is claimed here.

Per-user KiCad state files, autosaves, backup/cache files and operating-system metadata are excluded from version control.

## Tools and skills

`KiCad` · `STM32H743` · `Hierarchical Schematic Design` · `PT100 / MAX31865` · `Temperature Measurement` · `Power Distribution` · `Sensors` · `Motor Drivers` · `MOSFET Drivers` · `SSRs` · `Load Cells` · `Embedded Hardware Interfaces` · `Component Selection`
