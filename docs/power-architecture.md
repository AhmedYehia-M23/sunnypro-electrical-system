# Power architecture notes

This note documents the published power architecture of the SunnyPro electrical system and points to the editable KiCad source for the implementation details.

## Mains input and primary supply

The power schematic uses an IEC C14 mains inlet and an isolated **Mean Well IRM-60-24** AC/DC module as the main low-voltage source.

The IRM-60-24 is represented in the KiCad source as:

- output: **24 V DC**
- rated output current: **2.5 A**
- rated output power: **60 W**

The mains side also includes the protection and emergency-stop architecture shown in the schematic set.

## DC rails

The electrical system distributes the following rails across the machine:

- **24 V** — primary DC distribution rail
- **12 V** — derived subsystem rail
- **6 V** — derived subsystem rail
- **5 V** — derived subsystem rail
- **3.3 V** — logic rail

The 3.3 V section includes an **AMS1117-3.3** regulator in the published power schematic. Filtering and decoupling components are included around the derived rails.

## Design intent

The rail structure separates loads with different voltage requirements rather than forcing all actuators, sensors and logic onto a single supply. The architecture supports the machine's mix of:

- STM32 logic and digital interfaces
- sensors and measurement electronics
- motor and actuator interfaces
- HMI/peripheral electronics
- heating-control interfaces

## Protection strategy

The published schematic set includes the following protection concepts:

- RCCB / residual-current protection
- MCB / over-current protection
- emergency-stop path
- subsystem fusing
- flyback protection on inductive DC loads where applicable
- separation between mains-side switching/protection and low-voltage control electronics

## Evidence in the repository

The implementation can be inspected directly in:

- [`hardware/POWER.kicad_sch`](../hardware/POWER.kicad_sch)
- [`exports/SunnyPro-schematics.pdf`](../exports/SunnyPro-schematics.pdf)

The public portfolio release contains the electrical architecture and editable schematics. The original working calculation sheets used during the project are not included in this repository, so this document does not invent or reconstruct a detailed subsystem load budget after the fact.
