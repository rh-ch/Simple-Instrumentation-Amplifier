# Simple-Instrumentation-Amplifier | LTSpice

A three op-amp instrumentation amplifier designed and simulated in LTSpice, 
achieving a differential gain of 100 (40dB) with high common mode rejection.

## Circuit Overview

The classic three op-amp INA topology consists of:
- **Two input buffer op-amps (U1, U2)** — high input impedance buffers that 
  amplify the differential signal while passing common mode signals unchanged
- **Gain resistor (Rgain = 2.22kΩ)** — single resistor that sets the first 
  stage gain, calculated from the gain relation Av = (1 + 2R1/Rgain)(R3/R2)
- **Output difference amplifier (U3)** — rejects the common mode component 
  and outputs the amplified differential signal

## Specifications

| Parameter | Value |
|-----------|-------|
| Differential Gain | 100 (40dB) |
| CMRR | ~120dB |
| R1, R2 | 10kΩ |
| R3 | 100kΩ |
| Rgain | 2.22kΩ |

## Simulations

### Differential Mode
Two sinusoidal inputs with a 10mV difference — output produces 1V, 
confirming gain of 100.

[screenshot here]

### Common Mode Rejection
Identical signals applied to both inputs — output reduces to picovolts, 
demonstrating ~120dB CMRR. This confirms the amplifier's ability to reject 
noise common to both inputs while amplifying only the differential signal.

[screenshot here]

## Key Takeaways

- CMRR of ~120dB means common mode noise is rejected by a factor of one 
  million relative to the differential signal
- A single Rgain resistor controls gain, making this topology practical for 
  precision sensing applications
- High CMRR makes instrumentation amps the standard front-end for sensor 
  signal conditioning in noisy industrial environments
