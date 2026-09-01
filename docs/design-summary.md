# SunnyPro Electrical Architecture & Schematic Design Summary

## Role and Ownership

For the SunnyPro university group project, I was **solely responsible for the electrical architecture and all KiCad schematic design documented in this repository**. The overall machine was developed by the team, while the electrical architecture, subsystem interfaces, power planning and electrical component-selection work shown here were my responsibility.

The electrical schematic set was not supplied as pre-designed course material. I developed it from the machine requirements and organized it into hierarchical KiCad subsystems.

## Main Electrical Subsystems

### MCU
- STM32H743-based central controller
- Digital and analog supply separation/filtering
- Interfaces for sensors, motors, heating, actuators and HMI
- MCU I/O planning and signal allocation

### Power and Protection
- Protected AC mains input
- RCCB and MCB protection
- Emergency-stop path
- 24 V primary DC supply
- 12 V, 6 V, 5 V and 3.3 V derived rails
- Subsystem fusing and filtering
- Power-demand calculations and rail planning

### Temperature Measurement and Heating
- PT100 RTDs
- MAX31865 RTD interfaces
- SSR-controlled bottom heating
- SSR-controlled top IR heating
- Thermal protection and fusing

### Motion and Feedback
- NEMA17 + TB6600 conveyor drive
- Encoder feedback and home sensing
- 28BYJ-48 + ULN2003A rotating-plate drive
- Load cell + HX711 measurement

### Actuators and Peripherals
- MOSFET-switched solenoids with flyback protection
- Peristaltic pump control
- Servo actuation
- IR sensors and switches
- Serial HMI interface

## Engineering Workflow

The work included more than schematic capture. I mapped the machine requirements into electrical subsystems, defined MCU I/O, selected interfaces and drivers, estimated power demand, selected components, organized the protection scheme, created the hierarchical schematic structure and maintained consistency across the complete schematic set.

## Ownership Statement

**All electrical schematics and the electrical architecture presented in this repository were created by me.** The scope of this claim is the electrical architecture and schematic design; unrelated mechanical, software and other team-developed parts of the overall machine are outside this repository.
