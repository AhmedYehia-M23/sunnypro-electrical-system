# Key component selection

This is a compact list of the main electrical building blocks visible in the published SunnyPro schematic set. It is intended as a portfolio reference, not as a purchasing BOM.

| Function | Component / interface | Role in the system |
| --- | --- | --- |
| Main controller | STM32H743 | Central control and subsystem I/O |
| Main AC/DC supply | Mean Well IRM-60-24 | Isolated 24 V, 2.5 A, 60 W primary DC source |
| Logic regulation | AMS1117-3.3 | 3.3 V logic regulation in the power architecture |
| Temperature sensing | PT100 + MAX31865 | RTD measurement for heating subsystems |
| Conveyor drive | NEMA17 + TB6600 | Stepper-motor drive |
| Rotating mechanism | 28BYJ-48 + ULN2003A | Low-power stepper actuation |
| Load measurement | Load cell + HX711 | Weight/force measurement interface |
| Heater switching | Solid-state relays | MCU-controlled heater switching |
| DC actuators | MOSFET driver stages | Solenoids and pump switching with flyback protection |
| Position / presence sensing | IR sensors and home switches | Machine-state feedback |
| HMI | Serial interface | Operator-interface communication |

## Scope

The editable KiCad schematics remain the source of truth for references, values and connectivity. This file highlights the major engineering choices that are likely to be discussed in an interview.

A complete manufacturing/purchasing BOM is not included in the public portfolio release.
