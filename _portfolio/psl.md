---
title: "UAV-Mountable DFB laser based water vapor measurement system"
excerpt: "Integration of a UAV-mounted water-vapor sensing payload and design of a laser-driver protection circuit at the Photonic Sensors Lab, IIT Gandhinagar.<br/>>"
collection: portfolio
---

## The system

Measuring how water vapor changes with altitude needs a sensor that can fly. The lab uses wavelength-modulation spectroscopy (WMS): a DFB laser is tuned across a water absorption line near 1392 nm, and the absorption signal gives the water-vapor concentration. My part was the hardware that keeps the laser safe and the payload that carries it.  

## My role
I was the part of the Photonic Sensors Lab, IIT Gandhinagar where:
- **I Built:** The laser-driver protection circuit, from design to bench testing.
- **I contributed to:** Modifying the benchtop system and integrating the payload (laser driver, data acquisition, GSM module, power management) and the field trials.
- **Worked with:** Prof. Arup Lal Chakraborty, Dr. Shruti De, Dr. Pratik Prajapati Hiteshi Meisheri.


## Payload integration

The payload had to fit under the hexacopter and run on batteries. A Raspberry Pi runs the measurement algorithm, a PicoScope digitizes the photodetector signal, a 4G (GSM) module provides remote access, and buck converters supply the voltage levels each component needs. 

## Field trials

I took part in field trials of the system on a hexacopter, measuring atmospheric water vapor at about 100 ft.
This resulted in a publication of one conference paper (invited) and one journal paper (under review).

## Protection circuit: design and testing

- **Sensing:** [how current is sensed, such as a shunt resistor] read by a 16-bit ADC (ADS1115).
- **Trip logic:** at 115 mA the controller turns off a MOSFET and latches it off until a manual reset.
- **Why this approach:** The design is simple and the threshold value can be easily changed for different laser controller requirements. 

## Team 

![team photo](<../images/PSL team photo.jpeg>)

