# Hardware Requirements Specification (HRS)
## SCMATU – Ultrasonic Transducer Amplifier Hardware

**Project:** SCMATU – Sistema de Control y Medición de Amplificador para Transductor Ultrasónico  

---

# 1. Introduction

## 1.1 Purpose

This document defines the hardware requirements of the SCMATU system designed to:

- Excite a PZT ultrasonic transducer (or known RLC resonant circuit),
- Measure electrical parameters,
- Provide the necessary analog front-end for automatic resonance frequency determination.

This specification describes only hardware-level requirements. Firmware and software behavior are defined in their respective specifications.

---

# 2. System Objective

The hardware shall support automatic determination of the resonance frequency of a PZT transducer (or equivalent RLC circuit), defined as:

> The frequency at which the current through the device is maximum and in phase with the applied voltage.

---

# 3. Functional Hardware Requirements

---

## HR-01: Sinusoidal Excitation Capability

The hardware shall be capable of exciting the device under test (DUT) with a sinusoidal signal.

### HR-01.1 Frequency Range
The excitation stage shall support a variable frequency range sufficient to cover the expected resonance frequency of the PZT transducer or RLC test circuit.

### HR-01.2 Amplitude
The excitation output shall support a nominal amplitude of:

```
±10 V
```

This amplitude level is selected to be compatible with operational amplifiers powered at:

```
±12 V to ±15 V
```

### HR-01.3 Signal Quality
The excitation signal shall maintain acceptable sinusoidal integrity within the operating frequency range.

---

## HR-02: Voltage Measurement Capability

The hardware shall provide a measurement path for the voltage applied to the DUT.

### HR-02.1 Measurement Type
The measurement shall capture the peak voltage value.

### HR-02.2 Signal Conditioning
The voltage measurement stage shall:

- Scale the signal to match ADC input range.
- Provide appropriate filtering to reduce noise.
- Ensure safe voltage levels at the microcontroller input.

---

## HR-03: Current Measurement Capability

The hardware shall provide a measurement path for the current flowing through the DUT.

### HR-03.1 Measurement Method
Current shall be measured indirectly using a shunt resistor and signal conditioning stage.

### HR-03.2 Signal Conditioning
The current measurement stage shall:

- Amplify the shunt voltage appropriately.
- Scale the signal to the ADC input range.
- Provide filtering to reduce high-frequency noise.
- Ensure safe operation under expected current levels.

---

## HR-04: Phase Measurement Support

The hardware shall provide signals suitable for phase difference measurement between voltage and current.

### HR-04.1 Signal Availability
Both voltage and current measurement signals shall be accessible in a form suitable for:

- Zero-cross detection, or
- Time-based comparison using digital or analog thresholding.

### HR-04.2 Signal Integrity
The conditioning circuits shall preserve waveform shape sufficiently to allow accurate phase determination.

---

## HR-05: Frequency Sweep Support

The hardware shall support frequency sweeping across the configured operating range without:

- Excessive amplitude distortion,
- Thermal instability,
- Component saturation,
- Instability in the amplification stage.

---

# 4. Electrical Constraints

## EC-01: Supply Voltage

The hardware shall operate with supply rails compatible with:

```
±12 V to ±15 V (analog stage)
+5 V or +3.3 V (digital stage, depending on MCU design)
```

---

## EC-02: Safe Operating Limits

The hardware shall ensure:

- ADC inputs remain within microcontroller safe limits.
- Operational amplifiers remain within linear operating regions.
- The DUT is not exposed to unsafe overvoltage conditions under normal operation.

---

# 5. Measurement Accuracy Considerations

The hardware design shall:

- Minimize noise in voltage and current measurement paths.
- Ensure stable gain characteristics.
- Provide predictable scaling factors for firmware calibration.

Final phase precision and resonance determination accuracy depend on combined hardware and firmware implementation.

---

# 6. System Interfaces

The hardware shall provide:

- Interface to microcontroller ADC inputs.
- Interface to frequency generation module (e.g., DDS).
- Interface to power amplification stage.
- Electrical connection to DUT (PZT transducer or RLC test circuit).

---

# 7. Definitions

**DUT (Device Under Test):**  
PZT ultrasonic transducer or known RLC resonant circuit.

**Resonance Frequency:**  
Frequency at which current is maximum and phase difference between voltage and current approaches zero.

---
