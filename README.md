# 555-Timer-Astable-LED-Blinker-

# Overview

NE555 timer IC configured in astable mode — designed and verified in LTspice XVII using transient analysis. This simulation complements the physical PCB design in the 555-Timer-Astable-LED-Blinker repository, demonstrating a simulation-first design methodology where circuit behaviour is verified before a single PCB trace is routed.

## Circuit Specifications

Component      Value      Purpose
* U1           NE555      Timer IC
* V1           12V        DCSupply voltage
* R1           10kΩ       Charge resistor
* R2           10kΩ       Discharge resistor
* C1           47µF       Timing capacitor
* C2           10nF       Noise filter on CV pin
* R3           470Ω       LED current limiting resistor
* D1           LED        Visual output indicator

## Frequency Calculation
* f = 1.44 ÷ ((R1 + 2×R2) × C1)
* f = 1.44 ÷ ((10K + 2×10K) × 47µF)
* f = 1.44 ÷ (30000 × 0.000047)
* f = 1.44 ÷ 1.41
* f ≈ 1Hz
Component values calculated from first principles to achieve target 1Hz output — demonstrating deliberate component selection over trial and error.

## Simulation Results
Measurement        Value
* Supply voltage     12V 
* Output HIGH        ~12V 
* Output LOW         ~0V
* Waveform           Clean square wave
* Frequency          ~1Hz confirmed
* Signal quality     Sharp edges — no ringing

## Key Observations

* Clean square wave output confirmed — switching between 0V and 12V at approximately 1Hz, matching theoretical calculation exactly
* Frequency verified against hand-calculated result — simulation and formula agree, confirming correct component selection
* 10nF capacitor on CV pin effectively filters noise on the control voltage pin — producing stable, consistent oscillation with no frequency drift
* LED indicator driven correctly through 470Ω current limiting resistor — current verified within safe LED operating range
* Sharp switching edges with no ringing — confirming stable circuit behaviour and correct timing component values


Simulation Command : .tran 4

## What This Demonstrates

* 555 timer astable mode theory and operation
* Frequency calculation from first principles using timing formula
* Transient analysis in LTspice XVII for oscillator verification
* Simulation-first design methodology — verify before layout
* Relationship between simulation results and physical PCB design

<img width="1600" height="900" alt="Image" src="https://github.com/user-attachments/assets/f7fa7382-39b3-4d21-867f-75aee506be0c" />
