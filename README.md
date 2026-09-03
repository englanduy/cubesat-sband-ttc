# S-Band TT&C RF Subsystem for a 3U LEO CubeSat

## Overview

This project focuses on the **design and simulation of an S-band Telemetry, Tracking and Command (TT&C) RF subsystem for a 3U CubeSat operating in Low Earth Orbit (LEO)**.

The project follows a requirement-driven RF engineering workflow:

```text
Mission Requirements
        ↓
LEO Geometry
        ↓
Uplink / Downlink Link Budget
        ↓
RF Transmitter / Receiver Architecture
        ↓
RF Front-End Analysis
        ↓
S-Band RHCP Patch Antenna
        ↓
RF Receiver Front-End PCB
        ↓
System Verification
```

The project is intended to develop practical skills in satellite RF system design, link-budget engineering, RF front-end analysis, antenna simulation and RF PCB design.

---

## Mission Baseline

| Parameter                | Baseline     |
| ------------------------ | ------------ |
| Spacecraft               | 3U CubeSat   |
| Orbit                    | Circular LEO |
| Altitude                 | 550 km       |
| Function                 | TT&C         |
| Communication band       | S-band       |
| Uplink reference         | ~2.05 GHz    |
| Downlink reference       | ~2.23 GHz    |
| Modulation assumption    | BPSK         |
| Data rate                | 100 kbps     |
| Minimum design elevation | 10°          |
| Satellite antenna        | RHCP patch   |
| Target link margin       | ≥ 3 dB       |
| Receiver NF target       | ≤ 2 dB       |

The frequencies above are simulation reference values and do not represent operational frequency assignments.

---

## Project Scope

The project includes:

* Mission and RF subsystem requirements
* TT&C system architecture
* LEO geometry analysis
* Slant-range analysis
* Uplink link budget
* Downlink link budget
* LEO Doppler estimation
* RF transmitter architecture
* RF receiver architecture
* COTS RF component selection
* Cascaded RF gain analysis
* Receiver noise-figure analysis
* S-parameter analysis
* S-band RHCP patch-antenna design
* CST/HFSS electromagnetic simulation
* RF receiver front-end PCB design
* 50-ohm RF routing
* Requirement verification matrix
* Hardware RF test plan

---

## Out of Scope

The baseline project does not include:

* GNU Radio
* SDR/USRP hardware
* BER simulation
* Full CCSDS implementation
* FPGA/RFSoC
* Phased-array antennas
* Full transceiver PCB
* Physical PCB fabrication
* Physical RF measurements
* Space environmental qualification

These items may be considered as future extensions.

---

## RF Subsystem Concept

### Command Uplink

```text
Ground Station
      ↓
RF Transmitter
      ↓
Ground Antenna
      ↓
S-Band Uplink
      ↓
Satellite Antenna
      ↓
LNA
      ↓
BPF
      ↓
RF Receiver
      ↓
Command Interface
```

### Telemetry Downlink

```text
Telemetry Interface
      ↓
RF Transmitter
      ↓
PA
      ↓
BPF
      ↓
Satellite Antenna
      ↓
S-Band Downlink
      ↓
Ground Antenna
      ↓
Ground Receiver
```

---

## Engineering Targets

Initial design targets include:

| Parameter            | Target   |
| -------------------- | -------- |
| Uplink link margin   | ≥ 3 dB   |
| Downlink link margin | ≥ 3 dB   |
| Receiver cascade NF  | ≤ 2 dB   |
| Antenna S11          | ≤ −10 dB |
| Antenna VSWR         | < 2      |
| Antenna axial ratio  | ≤ 3 dB   |

These requirements may be refined after link-budget and subsystem trade studies.

---

## Repository Structure

```text
cubesat-sband-ttc/
│
├── requirements/
├── configs/
├── src/
├── tests/
├── link_budget/
├── rf/
├── antenna/
├── pcb/
├── verification/
└── docs/
```

### `requirements/`

Mission, subsystem requirements and project scope.

### `configs/`

Mission, uplink and downlink simulation parameters.

### `src/`

Python engineering-analysis code.

### `tests/`

Verification tests for analytical models.

### `link_budget/`

Link-budget spreadsheets, plots and reports.

### `rf/`

RF architecture, component selection and S-parameter analysis.

### `antenna/`

Antenna models and electromagnetic simulation results.

### `pcb/`

RF schematic, PCB layout and fabrication outputs.

### `verification/`

Requirement verification matrix and future hardware test procedures.

### `docs/`

System diagrams and final engineering documentation.

---

## Tools

### Engineering Analysis

* Python
* NumPy
* Pandas
* Matplotlib
* Excel

### RF Analysis

* Python / scikit-rf
* Qucs-S where required

### Antenna

* CST Studio Suite or ANSYS HFSS

### PCB

* Altium Designer

### Development

* Visual Studio Code
* Git
* GitHub
* pytest

---

## Project Roadmap

### Week 1

Requirements and system architecture.

### Week 2

LEO geometry and preliminary link budget.

### Week 3

Complete uplink/downlink link budgets, trade studies and Doppler analysis.

### Week 4

RF transmitter/receiver architecture, component selection, gain and noise analysis.

### Week 5

Initial S-band RHCP antenna design.

### Week 6

Antenna optimization and EM verification.

### Week 7

RF receiver front-end PCB design.

### Week 8

Subsystem integration, verification, RF test plan and final documentation.

---

## Verification Approach

Results in this project are explicitly classified as:

* Analytical
* Simulated
* Datasheet-derived
* Physically measured

The current project is software-based and does **not** include physical RF measurements.

Measurements requiring VNA, spectrum analyzer, signal generator or other laboratory equipment will therefore be identified as:

**NOT TESTED — Hardware validation required**

rather than being reported as experimentally verified.

---

