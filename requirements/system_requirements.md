# System Requirements v1.0

## S-Band TT&C RF Subsystem for a 3U LEO CubeSat

## 1. Purpose

This document defines the baseline system and RF requirements for the project:

**Design and Simulation of an S-Band TT&C RF Subsystem for a 3U LEO CubeSat**

These requirements provide traceability between the mission assumptions, link-budget analysis, RF subsystem design, antenna simulation, RF PCB design, and final verification activities.

Requirements may be refined if engineering analysis demonstrates that the original baseline is not technically consistent. Any modification shall be documented rather than silently changed.

---

# 2. Requirement Categories

The following requirement identifiers are used:

| Prefix | Category         |
| ------ | ---------------- |
| SYS    | System           |
| ORB    | Orbit / Geometry |
| COM    | Communication    |
| RF     | Radio Frequency  |
| ANT    | Antenna          |
| PCB    | RF PCB           |
| VER    | Verification     |

---

# 3. System Requirements

## SYS-001 — Spacecraft Platform

The communication subsystem shall be designed for a **3U CubeSat-class spacecraft**.

**Verification:** Design review

---

## SYS-002 — Mission Function

The subsystem shall support **Telemetry, Tracking and Command (TT&C)** communication between the CubeSat and a ground station.

**Verification:** Architecture review

---

## SYS-003 — Analysis Scope

The project shall model the **RF communication subsystem** rather than the complete spacecraft communication, flight software, or spacecraft bus.

**Verification:** Scope review

---

## SYS-004 — Implementation Method

The baseline project shall be implemented using **analytical calculations, software simulation, datasheet-derived component models, and PCB design tools**.

Physical RF measurements are outside the baseline scope.

**Verification:** Project review

---

# 4. Orbit and Geometry Requirements

## ORB-001 — Orbit Type

The baseline mission shall use a **circular Low Earth Orbit (LEO)**.

**Verification:** Configuration review

---

## ORB-002 — Orbit Altitude

The baseline orbit altitude shall be:

**550 km above mean Earth radius**

**Verification:** Configuration review

---

## ORB-003 — Elevation Analysis Range

The link-analysis model shall evaluate satellite elevation angles from:

**5° to 90°**

**Verification:** Python analysis

---

## ORB-004 — Minimum Design Elevation

The baseline RF link shall be evaluated against its design criteria at a minimum ground-station elevation angle of:

**10°**

**Verification:** Link-budget analysis

---

## ORB-005 — Slant Range

The geometry model shall calculate the satellite-to-ground-station slant range as a function of elevation angle.

**Verification:** Python analytical model

---

## ORB-006 — Doppler Analysis

The system model shall estimate the **S-band Doppler frequency shift associated with LEO satellite motion**.

The Doppler result shall be used to derive a receiver frequency-acquisition or tracking requirement.

**Verification:** Python analytical model

---

# 5. Communication Requirements

## COM-001 — Duplex Link Definition

The system shall model the following communication paths independently:

* Command uplink: Ground Station → CubeSat
* Telemetry downlink: CubeSat → Ground Station

**Verification:** Architecture review

---

## COM-002 — Communication Band

The baseline TT&C subsystem shall operate conceptually in the **S-band**.

**Verification:** Design review

---

## COM-003 — Uplink Simulation Frequency

The baseline uplink link-budget model shall use an approximate reference frequency of:

**2.05 GHz**

This value is intended for engineering simulation only and does not represent an authorized operational frequency assignment.

**Verification:** Configuration review

---

## COM-004 — Downlink Simulation Frequency

The baseline downlink link-budget model shall use an approximate reference frequency of:

**2.23 GHz**

This value is intended for engineering simulation only and does not represent an authorized operational frequency assignment.

**Verification:** Configuration review

---

## COM-005 — Modulation Assumption

The baseline link budget shall assume **BPSK modulation**.

No baseband BPSK modulator or demodulator implementation is required within the current project scope.

**Verification:** Link-budget configuration review

---

## COM-006 — Baseline Data Rate

The baseline information bit rate shall be:

**100 kbps**

The design shall allow the data rate to be varied during link-budget trade studies.

**Verification:** Link-budget analysis

---

# 6. RF Link Requirements

## RF-001 — Uplink Link Margin

The simulated command uplink shall achieve a minimum link margin of:

**3 dB**

at the baseline design condition.

**Verification:** Uplink link-budget analysis

---

## RF-002 — Downlink Link Margin

The simulated telemetry downlink shall achieve a minimum link margin of:

**3 dB**

at the baseline design condition.

**Verification:** Downlink link-budget analysis

---

## RF-003 — Link-Budget Parameters

The uplink and downlink models shall calculate at least:

* Slant range
* Free-space path loss
* Transmitter EIRP
* Received carrier power
* Receiver system noise temperature
* Receiver G/T
* C/N0
* Eb/N0
* Required Eb/N0
* Link margin

**Verification:** Link-budget code review and output inspection

---

## RF-004 — Receiver Noise Figure

The CubeSat receiver RF front-end shall target a cascaded noise figure of:

**≤ 2 dB**

This value is an initial design target and may be refined following component selection and link-budget analysis.

**Verification:** Cascaded noise-figure calculation

---

## RF-005 — RF Gain Budget

The transmitter and receiver RF chains shall have documented gain and loss budgets.

The analysis shall include component gains, insertion losses, and relevant passive losses.

**Verification:** RF cascade analysis

---

## RF-006 — RF Component Selection

RF active and passive components shall be selected from identifiable commercial components where possible.

Component selection shall consider at least:

* Operating frequency
* Gain or insertion loss
* Noise figure where applicable
* Output power where applicable
* Input/output matching
* Supply requirements
* Availability of manufacturer documentation

**Verification:** Component-selection review

---

## RF-007 — S-Parameter Analysis

Where manufacturer Touchstone data are available, RF component or network performance shall be evaluated using S-parameters.

The analysis shall include at least:

* S11
* S21

where applicable.

**Verification:** scikit-rf, Qucs-S, or equivalent simulation

---

# 7. Antenna Requirements

## ANT-001 — Antenna Type

The CubeSat baseline antenna shall be an **S-band microstrip patch antenna**.

**Verification:** Antenna design review

---

## ANT-002 — Polarization

The satellite antenna shall target **Right-Hand Circular Polarization (RHCP)**.

**Verification:** CST/HFSS electromagnetic simulation

---

## ANT-003 — Input Matching

The simulated antenna shall target:

**S11 ≤ −10 dB**

at the selected operating frequency.

**Verification:** CST/HFSS electromagnetic simulation

---

## ANT-004 — VSWR

The simulated antenna shall target:

**VSWR < 2**

at the selected operating frequency.

**Verification:** CST/HFSS electromagnetic simulation

---

## ANT-005 — Axial Ratio

The antenna shall target an axial ratio of:

**≤ 3 dB**

in the intended communication direction.

**Verification:** CST/HFSS electromagnetic simulation

---

## ANT-006 — Antenna Gain

The antenna realized-gain requirement shall be derived from the completed link budget.

The antenna design shall demonstrate that its simulated gain is consistent with the RF link requirement.

**Verification:** Link-budget analysis + CST/HFSS simulation

---

## ANT-007 — Radiation Performance

The antenna analysis shall include:

* 3D radiation pattern
* Principal-plane radiation patterns
* Realized gain
* Radiation efficiency
* Polarization performance

**Verification:** CST/HFSS simulation

---

# 8. RF PCB Requirements

## PCB-001 — PCB Scope

The baseline PCB shall implement an **S-band receiver RF front-end**, rather than a complete satellite transceiver.

**Verification:** PCB architecture review

---

## PCB-002 — Baseline RF Chain

The baseline PCB shall contain the conceptual signal path:

**RF Input → Protection/Limiter → LNA → Band-Pass Filter → RF Output**

Components may be revised following RF-chain analysis.

**Verification:** Schematic review

---

## PCB-003 — Characteristic Impedance

RF transmission lines shall be designed for a nominal characteristic impedance of:

**50 Ω**

**Verification:** Stackup and impedance calculation

---

## PCB-004 — RF Grounding

The RF PCB shall use a continuous RF ground strategy and appropriate ground vias.

**Verification:** Layout review

---

## PCB-005 — Via Fencing

Via fencing shall be considered along critical RF transmission-line sections where appropriate.

**Verification:** Layout review

---

## PCB-006 — Power Decoupling

Active RF components shall include appropriate bias and supply decoupling based on manufacturer recommendations.

**Verification:** Schematic and layout review

---

## PCB-007 — RF Connector Interface

The RF board shall provide a defined 50-Ω RF interface using an SMA or equivalent connector.

**Verification:** Schematic and layout review

---

## PCB-008 — Fabrication Outputs

The PCB project shall generate fabrication-oriented outputs, including at least:

* Schematic PDF
* PCB layout
* Stackup definition
* Gerber files

**Verification:** Design-file review

---

# 9. Verification Requirements

## VER-001 — Requirement Traceability

Each core technical requirement shall be associated with a verification method.

**Verification:** Verification matrix review

---

## VER-002 — Result Classification

Project results shall be classified as one of:

* Analytical
* Simulated
* Datasheet-derived
* Physically measured

**Verification:** Documentation review

---

## VER-003 — Measurement Integrity

No parameter shall be identified as physically measured unless an actual hardware measurement has been performed.

**Verification:** Final report review

---

## VER-004 — Hardware Validation Status

Requirements requiring unavailable laboratory equipment shall be identified as:

**NOT TESTED — Hardware validation required**

**Verification:** Verification matrix review

---

## VER-005 — Hardware Test Plan

The final project shall include proposed test procedures for future hardware validation.

The test plan shall address at least:

* Antenna S11 measurement using a VNA
* RF front-end S21 measurement
* RF gain measurement
* Transmitter output-spectrum measurement
* Transmitter output-power measurement

**Verification:** RF test-plan review

---

# 10. Requirement Status

At Project Scope v1.0, the requirements are classified as:

| Status   | Meaning                                                |
| -------- | ------------------------------------------------------ |
| PROPOSED | Initial requirement requiring engineering confirmation |
| BASELINE | Requirement currently accepted for project design      |
| DERIVED  | Requirement derived from another engineering analysis  |
| TBD      | Value not yet determined                               |

Initial status:

| Requirement       | Status        |
| ----------------- | ------------- |
| SYS-001 – SYS-004 | BASELINE      |
| ORB-001 – ORB-006 | BASELINE      |
| COM-001 – COM-006 | BASELINE      |
| RF-001 – RF-003   | BASELINE      |
| RF-004            | PROPOSED      |
| RF-005 – RF-007   | BASELINE      |
| ANT-001 – ANT-005 | BASELINE      |
| ANT-006           | DERIVED / TBD |
| ANT-007           | BASELINE      |
| PCB-001 – PCB-008 | BASELINE      |
| VER-001 – VER-005 | BASELINE      |

---

# 11. Requirement Refinement Rule

A baseline numerical value may be changed if subsequent engineering analysis demonstrates that the current value is unsuitable.

For example:

Link budget
→ required antenna gain
→ antenna feasibility analysis
→ revised antenna requirement.

Any such change shall be:

1. Justified by engineering analysis.
2. Recorded in project documentation.
3. Reflected in the requirement status or revision.
4. Propagated to dependent subsystem requirements.

Requirements shall not be modified solely to make simulation results pass.
