# Top Slot Power  

A multi source capable power supply for PSION Organiser II (all family) devices with power failure memory saver. The design reduces risk of internal device memory loss either due to external power interruption or due to Lithium 9 Volt surrogate battery discharge characteristics (limited if any warning). By providing sufficient standby power for longer term internal memory retention and specifically not operation. Permitting hours / days for recharge of main power battery or months of power down whilst preserving the internal RAM contents. The design (should) fits a classic PSION Organiser II Top Slot Case (See all notes).
<BR>
<div align="center">
  <div style="display: flex; align-items: flex-start;">
  <img src="https://github.com/nofitnessforpurpose/TopSlotPower01/blob/main/photos/ONE-PSU-TRTA-01.jpg?raw=true" width="400px" alt="PSION Organiser II Top Slot Battery Saver. Image copyright (c) 14 December 2024 nofitnessforpurpose All Rights Reserved">
  </div>
</div>
<BR>

[![Organiser](https://img.shields.io/badge/gadget-Organiser_II-blueviolet.svg?%3D&style=flat-square)](https://en.wikipedia.org/wiki/Psion_Organiser)
[![GitHub License](https://img.shields.io/github/license/nofitnessforpurpose/TopSlotPower01?style=flat-square)](https://github.com/nofitnessforpurpose/TopSlotPower01/blob/main/LICENSE)
[![Maintenance](https://img.shields.io/badge/maintained%3F-yes-green.svg?style=flat-square)](https://github.com/nofitnessforpurpose/TopSlotPower01/graphs/commit-activity)
![GitHub repo size](https://img.shields.io/github/repo-size/nofitnessforpurpose/TopSlotPower01?style=flat-square)
[![Static Badge](https://img.shields.io/badge/format-GERBER-blue?style=flat-square)](https://en.wikipedia.org/wiki/Gerber)

<br>  
<br>  
All the files are required for a complete assembly.  
<BR>
 - The default repository format is STEP (<a target="_blank" rel="noopener noreferrer" href="https://en.wikipedia.org/wiki/ISO_10303"> ISO 10303</a> ) due to its high fidelity.  
<BR>
 &nbsp;&nbsp;&nbsp;&nbsp;{ STL files are surface geometry as opposed to solid model representations, often containing export processing artifacts }. <br>  
 - The default repository format for PCB files is <a targer="_blank" rel="noopener noreferrer" href="https://en.wikipedia.org/wiki/Gerber_format">GERBER</a> .
<BR>

<BR>
<a target="_blank" rel="noopener noreferrer" href="https://www.freecad.org/" > FreeCAD </a> may prove suitable for viewing, handling and, if desired modifying STEP files.
<BR>
<a target="_blank" rel="noopener noreferrer" href="https://www.kicad.org/" >KiCad </a> may prove suitable for viewing GERBER files.
<BR>
<BR>

## Implementation
The design presents a multi source capable power system for the Top Slot of a PSION Organiser II family of devices. Along with power source capability from the classic Barrel jack 10.4 Volt power supply and a USB-C connnection, a memory protection feature is included to protect the devices internal RAM memory. In the event of power loss / removal, internal RAM memory would be matained for up to 12 months together with time keeping functionality.  

The PCB dimensions (38.0 x 43.6 mm) are ideally suited to low cost manufacture. The 4 layer PCB design provides low cost of implementation. Whilst the PCB space claim is intended to be suitable for a classic <a target="_blank" rel="noopener noreferrer" href="https://github.com/nofitnessforpurpose/TopSlotCase">Top Slot Case </a> (See Considerations) and construction is surface mount and through hole PCB based for ease of assembly.  

The through hole technology allows straight forward assembly of Barrel Jack and memory protection feature. Whilst the more advanced surface mount features are required for the USB-C power source. The design will operate as a memory saver device without the surface mount components, though <a target="_blank" rel="noopener noreferrer" href="https://github.com/nofitnessforpurpose/TopSlotBatterySaverBasic">this design</a> might be preferred in such circumstances.  

<BR>

A minimum configuration comprises:  
- a 4 layer PCB  
- 1N4148 diode
- 2 battery clips
- 2 x 8 way Right angle header (~8 mm engagement length)
- 2 off CR2032 batteries or similar

<BR>

### Device Power Sources  
Device power is prioritised to select from the various sources in the following order of priority:
 - Classic Barrel Jack
 - USB-C
 - Internal 9 Volt source
 - Memory protection system
   
#### USB-C  
A USB-C connection is provided using basic 5 Volt capability only to provide maximum compatibility and obviate endpoint power management systems. A high quality buck boost power system with additional over voltage protection. Provides an additional feature to protect against USB-C Power Delivery over voltage scenarios.

#### Barrel Jack  
A classic Barrel Jack (5.5 mm outer, 2.0 mm pin) connector for the ~10.4 Volt 175 milli Amp centre positive pin power supply is located to be compatible with the classic Top Slot Case. The Barrel Jack connections are brought to 2 header pins on the left of the PCB to permit alternate power sources to be readily accommodated. (This is the same connector used on the classic Arduino Uno and Mega boards).  

### Power Backup
A low voltage 'secondary' power source is held on the PCB to allow for longer term retention when the main power supply or internal PP3 battery become depleted. Switching is automatic via diodes and the purposefully lower secondary battery level restricts usage to notification and memory backup only.  

<BR>
