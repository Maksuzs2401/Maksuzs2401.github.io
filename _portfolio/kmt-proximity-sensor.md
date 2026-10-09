---
title: "Inductive Proximity Sensor and Logic Converter"
excerpt: "End-to-end design of an industrial inductive proximity sensor, and Prototype development of logic converter module at KMT.<br/>>"
collection: portfolio
---
**Role:** R&D Engineer, KMT (Krishna Machine Tools), Jul 2025 – Jul 2026

I designed an inductive proximity sensor end to end: the analog circuit, the debugging, the validation rig, and the pilot production run. Additionally, I designed a logic converter module that can translate between any four type of PLC logic types.

![Finished sensor](/images/sensormodule.jpeg)

## Problems found and fixed

- **Oscillator thermal drift** I solved it by fine tuning the BJT biasing inorder to get stable sine wave.
- **Rectifier RC drift** caused unstable switching. I retuned the resistor value, reducing the RC time constant.
- **Touch-induced EMI.** Touching the metal housing put spikes on the signal line. A grounded Faraday shield (foil insulated on both sides, tied to PCB ground) between the PCB and housing eliminated it. In the new design the PCB traces were redesigned with proper gorund pour.

## Endurance test

I built a test rig to prove reliability: a T-shaped moving rod 7 mm from the sensing face, with the sensor output stepped down from 24 V to 5 V through a resistor divider into an Arduino Uno. Counts were saved to EEPROM every 1000 counts so a power cut would not lose them.

**Result:** 12 million switching cycles over 5 days of continuous operation at 12 V DC and 27 °C, with zero failures. The test was still running when it ended.

## Field testing

The sensor module was fitted on a designer tile machine, where it detects the position of the hydraulic press and signals the machine's controller. The units operated in a harsh industrial environment, with high temperatures and fine dust.

<video controls muted playsinline preload="metadata"
       style="width:100%; max-width:560px; height:auto; display:block; margin:0 auto;">
  <source src="/files/sensor_field_testing.mp4.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>
## Pilot production

I set up the assembly and QC flow for a 600-unit pilot run and wrote the technical design and production-transfer report.

## PLC logic converter module

PLC inputs expect a specific sensor output type: sinking (NPN) or sourcing (PNP), and normally open (NO) or normally closed (NC). A mismatch means the sensor can't be used as it is. I designed a small inline module that fits between the sensor and the PLC input and converts between all four configurations (NPN-NO, NPN-NC, PNP-NO, PNP-NC), so a sensor can be used with a PLC input of either type.
