# Top Slot Power  

A multi power source capable power supply for PSION Organiser II (all family) devices with power failure memory saver. The design reduces risk of internal device memory loss either due to external power interruption or due to Lithium 9 Volt surrogate battery discharge characteristics (limited if any warning). By providing sufficient standby power for longer term internal memory retention and specifically not operation. Permitting hours / days for recharge of main power battery or months of power down whilst preserving the internal RAM contents. The design (should) fits a classic PSION Organiser II Top Slot Case with minor modification for the USB connection (See all notes).
<BR>
<div align="center">
  <div style="display: flex; align-items: flex-start;">
  <img src="https://github.com/nofitnessforpurpose/TopSlotPower01/blob/main/photos/ONE-PSU-TRTA-05.jpg?raw=true" width="400px" alt="PSION Organiser II Top Slot Battery Saver. Image copyright (c) 14 December 2024 nofitnessforpurpose All Rights Reserved">
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

The PCB dimensions (38.0 x 43.6 mm) are ideally suited to low cost manufacture. The 4 layer PCB design provides low cost of implementation. Whilst the PCB space claim is intended to be suitable for a classic <a target="_blank" rel="noopener noreferrer" href="https://github.com/nofitnessforpurpose/TopSlotCase">Top Slot Case with minor modification </a> (See Considerations) a custom case is avilable in the repository, construction is surface mount and through hole PCB.    

The through hole technology allows straight forward assembly of Barrel Jack and memory protection feature. Whilst the more advanced surface mount features are required for the USB-C power source. The design will operate as a memory saver device without the surface mount components, though <a target="_blank" rel="noopener noreferrer" href="https://github.com/nofitnessforpurpose/TopSlotBatterySaverBasic#testing">this design</a> might be preferred in such circumstances.  

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

#### Power Backup  
A low voltage 'secondary' power source is held on the PCB to allow for longer term retention when the main power supply or internal PP3 battery become depleted. Switching is automatic via diodes and the purposefully lower secondary battery level restricts usage to notification and memory backup only.  

Details on testing and backup battery performance are located in the <a target="_blank" rel="noopener noreferrer" href="https://github.com/nofitnessforpurpose/TopSlotBatterySaverBasic#testing">Top Slot Battery Saver Basic</a> repository.

### Software
The device is transparent to the Organiser's Operating system and requires no software to operate.  

### Connection
It is preferable to avoid conneting the unit with no power source avilable e.g. absence of 9 Volt internal battery or power sourced via the units power connections i.e. 10.4 Volt Barrel Jack connection or USB-C connection. So as to avoid unecessarily discharging the backup batteries. By providing a main power source on connection of the unit. The internal capacitors of the Orgnaiser are 'pre-charged' from the main power source rather than the backup battery system, thus ensuring maximum life and thus protection.

Use of a <a target="_blank" rel="noopener noreferrer" href="https://en.wikipedia.org/wiki/Battery_pack#Power_bank">battery bank</a> to power the Orgnaiser will require a 'Keep-Alive' device (effecively a 555 timer plus low value resistance). The power drawn by the Organisers normal use is far too low for battery banks typical auto shut down features.  

### Battery use
Remove batteries from unused devices.
Also see <a target="_blank" rel="noopener noreferrer" href="https://github.com/nofitnessforpurpose/TopSlotBatterySaverBasic#stored-energy-use">here</a>.

<BR>

## Testing
Thermal evaluation of the device under full load (100 mA) conditions was performed to assess the temperature rise of the regulator and diode of the USB boost voltage regulator system. The input USB voltage was 4.9610 Volts at the PCB (5.250 Volts no load - 3 m USB cable), 10.118 Volts from the boost regulator output with the SVB voltage was 9.332 Volts presented to the load bank.

Following 2 hours of load a maximum thermal rise of 10 C at 25 C room ambient was observed. The image was captured at this point, noting that the metal components surface finish alias temperature indication, as shown by the battery and holder having distinctly differing temperatures. The image is for indication only, with measurements taken using a 0.8 mm dia. welded bead thermocouple.
<div align="center">
  <div style="display: flex; align-items: flex-start;">
  <img src="https://github.com/nofitnessforpurpose/TopSlotPower01/blob/main/photos/2025-01-27%20-%20100%20mA%202%20Hour%20Full%20Load%20Test%20-%20Max%2040%20C.png?raw=true" width="400px" alt="PSION Organiser II Top Slot Battery Saver. Image copyright (c) 14 December 2024 nofitnessforpurpose All Rights Reserved">
  </div>
</div>
<BR>

As anticipated, the regulator and diode are the heat sources, the thermal image shows good heat soak into the PCB and additionally into the USB connector and its over mould.

Voltage regulation output voltage was found to be better than 0.3% between no load and full load. Effective voltage regulation at SVB was 0.5%.

Near Field H Probe indication of the Rev 0.1 unit confirmed expectations that under typical operating conditions the units emissions were low / undetectable (i.e. orders of magnitude lower than a co-located Arduino Nano). At full load, the magnetics and current flow gave rise to a characteristic ~150 MHz trace shown. Principally located at the boost convertor inductor and output capacitor. A future iteration will attempt to improve the full load performance somewhat by additionally targeting the output filters performance during full load. At ~ 5 cm from the device no appreciable H-Field signal was evident. Note the trace recorded with the device connected to a passive load frame. 

<div align="center">
  <div style="display: flex; align-items: flex-start;">
  <img src="https://github.com/nofitnessforpurpose/TopSlotPower01/blob/main/photos/2027-01-28%20-%20OPSTRTA%20-%20NF%20H%20Probe%2010%20mm%20LOOP%20Probe.png?raw=true" width="400px" alt="PSION Organiser II Top Slot Battery Saver. Image copyright (c) 14 December 2024 nofitnessforpurpose All Rights Reserved">
  </div>
</div>
<BR>
<BR>

In some aspects, especially the lower frequency band, the performance was better than an EBL 5400 mWh battery (6F22 9V boost converter type) under similar load conditions and particularly under step load change conditions typical of the type occurring during EPROM programming!

The H Field probe was maintained parallel to the top of PCB for assessment repeatability, this may not represent the highest amplitude. The lower side of the PCB exhibited levels ~ 1/3 of those on the upper side.  

<BR>

## Considerations

When running at higher current loads these are outside the efficient normal operating range of the device. The design is intended for typical use, i.e. which does not involve continuous high current loads. The nominal 20 mA load current is more than sufficient for the majority of Organiser use cases. The relatively short period EPROM programming loads can typically be readily accepted with the reduced efficiency of the voltage conversion, which under 100 mA load can fall to as low as 80% (from 90%). Use of high quality capacitors is particularly recommended to accommodate ripple current typically arising from EPROM programming. A typical duty cycle might be of the order of 10%, though 24 hour (room temperature) <a target="_blank" rel="noopener noreferrer" href="https://en.wikipedia.org/wiki/Burn-in">burn in</a> testing has been completed in order to demonstrate design robustness.  

Models or files makes no accommodation for manufacturing tolerances, process or material - see Notes below.  

The original male 8 way 2 row top slot header style connector (marked MXS 70224) may have included a custom pin support moulding. Data from a parts list kindly indicated in this <a target="_blank" href="https://www.organiser2.com"> hardware forum</a> seemed to confirm this theory. Readily available 8 way 2 row header connectors tend to have smaller pin support mouldings. The effect of using pin headers with smaller moulding is to permit the PCB to displace vertically in the slot guide channel, resulting in poor alignment with the mating female connector and potential insertion difficulty. There are a number of mitigations, such as changing the height of the male header connector in the PCB and adding material to support the top of a smaller male header pin support moulding. The precise accommodation will depend on your selected pin header moulding, also see <a  target="_blank" rel="noopener noreferrer" href="https://github.com/nofitnessforpurpose/TopSlotCase-2">here</a>.  

Connecting any device which has not undergone thorough testing, will lead to irreversible degradation!  

<BR>

## Questions / Discussion
See <a target="_blank" rel="noopener noreferrer" href="https://www.organiser2.com/"> Organiser 2 Hardware </a> forum, though see note below first.

<BR>

## Please note:  
Such a system does not obviate the need for standard good practice backup procedures.  
Assessment for any fitness for purpose is entirely the users responsibility. Use is entirely at the users own risk. Any degradation to hardware, data loss or corruption is the responsibility of the user.

All information is For Indication only.
No association, affiliation, recommendation, suitability, fitness for purpose should be assumed or is implied.
Registered trademarks are owned by their respective registrants.

