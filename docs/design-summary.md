# SunnyPro Electrical Design Summary

SunnyPro was an HSRW group project. This document summarizes the electrical architecture and schematic work published in this repository; the separate [`SOURCE_OWNERSHIP.md`](../SOURCE_OWNERSHIP.md) file records the contribution boundary.

## MCU and interfaces

- STM32H743-based central controller
- digital and analog supply separation/filtering
- interfaces for sensors, motors, heating, actuators and HMI
- MCU I/O planning and signal allocation

## Power and protection

- IEC mains input and protected AC path
- RCCB and MCB protection concepts
- emergency-stop path
- Mean Well IRM-60-24 primary 24 V DC supply
- 24 V, 12 V, 6 V, 5 V and 3.3 V rails
- subsystem fusing and filtering

See [`power-architecture.md`](power-architecture.md) for a focused summary.

## Temperature measurement and heating

- PT100 RTDs
- MAX31865 RTD interfaces
- SSR-controlled bottom heating
- SSR-controlled top IR heating
- thermal protection and fusing interfaces

## Motion and feedback

- NEMA17 + TB6600 conveyor drive
- encoder feedback and home sensing
- 28BYJ-48 + ULN2003A rotating-plate drive
- load cell + HX711 measurement

## Actuators and peripherals

- MOSFET-switched solenoids with flyback protection
- pump control
- servo actuation
- IR sensors and switches
- serial HMI interface

## Engineering workflow

The machine requirements were divided into electrical subsystems, mapped to MCU I/O, assigned to appropriate power rails and organized into a hierarchical KiCad schematic structure. The work also required selecting sensor/actuator interfaces, protection elements and driver stages while maintaining consistent power and signal naming across the schematic set.

The editable KiCad files are the main engineering evidence in this portfolio release. A compact list of the major component choices is available in [`key-components.md`](key-components.md).
