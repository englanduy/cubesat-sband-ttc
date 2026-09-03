# Project Scope v1.0

## Project Title

**Design and Simulation of an S-Band TT&C RF Subsystem for a 3U LEO CubeSat**

## 1. Project Objective

The objective of this project is to design and simulate the radio-frequency subsystem of an S-band Telemetry, Tracking and Command (TT&C) communication system for a 3U CubeSat operating in Low Earth Orbit (LEO).

The project focuses on RF system engineering rather than full spacecraft or baseband implementation.

The main engineering workflow is:

Requirements → LEO Geometry → Link Budget → RF Architecture → RF Front-End → Antenna → RF PCB → Verification.

## 2. Mission Baseline

The initial mission baseline is:

| Parameter                            | Baseline                                 |
| ------------------------------------ | ---------------------------------------- |
| Spacecraft                           | 3U CubeSat                               |
| Orbit                                | Circular LEO                             |
| Altitude                             | 550 km                                   |
| Mission function                     | TT&C                                     |
| Communication band                   | S-band                                   |
| Uplink reference frequency           | approximately 2.05 GHz                   |
| Downlink reference frequency         | approximately 2.23 GHz                   |
| Modulation assumption                | BPSK                                     |
| Baseline data rate                   | 100 kbps                                 |
| Minimum design elevation             | 10°                                      |
| Analysis elevation range             | 5°–90°                                   |
| Satellite antenna                    | RHCP patch antenna                       |
| Ground antenna                       | Directional circularly polarized antenna |
| Target link margin                   | ≥ 3 dB                                   |
| Receiver cascade noise figure target | ≤ 2 dB                                   |
| Antenna S11 target                   | ≤ −10 dB                                 |
| Antenna VSWR target                  | < 2                                      |
| Antenna axial-ratio target           | ≤ 3 dB                                   |
| Implementation method                | Software-based design and simulation     |

The selected uplink and downlink frequencies are simulation reference values only and do not represent an authorized frequency assignment for an operational satellite.

## 3. Included Scope

### WP1 — Requirements and System Architecture

The project shall include:

* Mission baseline definition
* RF subsystem requirements
* Independent uplink and downlink definitions
* TT&C system architecture
* RF subsystem block diagrams
* Requirement traceability

### WP2 — LEO Geometry and Link Budget

The project shall include:

* Earth and satellite geometry
* Slant-range calculation
* Elevation-angle analysis
* Free-space path loss
* EIRP
* Received carrier power
* System noise temperature
* Receiver G/T
* C/N0
* Eb/N0
* Required Eb/N0 assumption
* Link margin
* Separate uplink link budget
* Separate downlink link budget
* Parameter trade studies
* Analytical LEO Doppler estimation

### WP3 — RF Transmitter and Receiver Design

The project shall include:

* RF transmitter architecture
* RF receiver architecture
* LNA
* PA
* Band-pass filter
* RF switch / T/R switching concept
* Mixer or RF transceiver concept where appropriate
* COTS RF component selection
* Cascaded gain analysis
* Cascaded receiver noise-figure analysis
* Output-power analysis
* Basic S-parameter analysis using manufacturer data where available

### WP4 — S-Band Antenna

The project shall include:

* Antenna requirement derivation from link budget
* S-band microstrip patch antenna
* Circular polarization
* CST or HFSS electromagnetic simulation
* S11
* VSWR
* Smith chart
* Realized gain
* Radiation pattern
* Efficiency
* Axial ratio
* Antenna optimization

Only one satellite antenna design will be developed in the baseline project.

### WP5 — RF Receiver Front-End PCB

The PCB scope is limited to an RF receiver front-end rather than a complete satellite transceiver.

Baseline architecture:

SMA Input → Protection / Limiter → LNA → Band-Pass Filter → SMA Output

The PCB design shall address:

* Schematic design
* COTS component footprints
* RF stackup
* 50-ohm controlled impedance
* Microstrip or coplanar-waveguide routing
* Continuous ground plane
* Via fencing
* RF component placement
* Decoupling and bias networks
* SMA transition
* Fabrication outputs such as Gerber files

### WP6 — Verification and Hardware Test Plan

The project shall include:

* Requirement verification matrix
* Analytical verification
* Simulation-based verification
* Comparison between subsystem requirements and achieved performance
* Proposed VNA test procedure
* Proposed spectrum-analyzer test procedure
* Proposed RF gain measurement
* Proposed antenna S11 measurement
* Identification of parameters that require future hardware validation

## 4. Explicitly Excluded Scope

The following items are intentionally excluded from Project Scope v1.0:

* GNU Radio implementation
* SDR hardware implementation
* USRP
* BPSK transmitter implementation
* BPSK receiver implementation
* BER simulation
* Constellation analysis
* Carrier synchronization
* Timing synchronization
* Telemetry decoder
* Full CCSDS implementation
* FEC implementation
* FPGA implementation
* Zynq RFSoC implementation
* Phased-array antenna
* Helical antenna
* Deployable antenna
* Full RF transceiver PCB
* Transistor-level LNA design
* Transistor-level PA design
* CubeSat OBC design
* EPS design
* ADCS design
* Payload design
* Physical PCB fabrication
* Physical antenna fabrication
* VNA measurements
* Spectrum-analyzer measurements
* Signal-generator measurements
* Power-meter measurements
* Anechoic-chamber measurements
* Thermal-vacuum qualification
* Vibration and shock qualification
* Radiation qualification
* Detailed ITU filing
* Flight qualification

These functions may be considered as future extensions after the baseline eight-week project has been completed.

## 5. Design Philosophy

The project follows a requirement-driven engineering process.

Each major design choice should be justified through engineering analysis rather than copied directly from an existing CubeSat design.

For example:

Required link margin
→ required EIRP
→ required satellite antenna gain
→ required transmitter output power
→ PA selection.

Similarly:

Received carrier level
→ receiver sensitivity requirement
→ allowable receiver noise figure
→ LNA and RF-chain selection.

## 6. Verification Philosophy

Results shall be classified as:

* Analytical
* Simulated
* Datasheet-derived
* Physically measured

Because no RF laboratory equipment is available for the baseline project, no physically measured result shall be claimed.

Parameters requiring physical validation shall be marked:

**NOT TESTED — Hardware validation required**

## 7. Project Duration

Target duration:

**8 weeks**

The project is divided into:

* Week 1 — Requirements and architecture
* Week 2 — LEO geometry and preliminary link budget
* Week 3 — Complete uplink/downlink link budget and Doppler
* Week 4 — RF Tx/Rx architecture and component analysis
* Week 5 — Antenna design
* Week 6 — Antenna simulation and optimization
* Week 7 — RF front-end PCB
* Week 8 — Integration, verification, documentation and portfolio preparation

## 8. Scope Freeze

This document defines **Project Scope v1.0**.

No major subsystem shall be added before completion of WP1–WP6.

Any additional feature shall be recorded as future work rather than added to the baseline project.
