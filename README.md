Aim
===
- Create a IDE to SATA bridge PCB with pass-through socket for XBox DVD cable.

Motivation
==========
- Remove the need for a 80 wire IDE cable
- Use existing IDE cable for DVD drive

Completed
=========
- Unverified schematic of Startech IDE2SATA pcb
- Startech IDE2SATA layer scans and annotations in GIMP .xcf image format.

To do
=====
Measure components;
- L1

- Find suitable 3V3 and ground points to tap on XBox motherboards
- Measure available space inside XBox under DVD drive.
  - there is/are a radial capacaitor/s close to the IDE header
    - I would like to not make a hole in the PCB for matched IDE to IDE routing lengths
    - The capactor/s have enough leg legnth to pull up and lay flat

- Can xbox ide connection be directly connected to DVD connection?
  - Simular how a IDE cable does?
  - IDE cable does have CSEL tied hi or low depending on device?
- Can LED circuit be removed? Is it for HDD activity?
- CSEL cable selection can be fixed as DVD will always be device 0 (slave) and SATA device 1 (master)?
- What capacitors are required for power input from xbox motherboard?

Requirements
============
- Marvell 88SA8052 - NNC2 IC
  -  PATA/ATAPI to SATA bridge chip W/ATAPI, 3 GBps SATA
     -  64 pin
     -  package: PQFN50P900X900X90-65
  - 1V2 Voltage regulator for Marvel IC Vdd
  - 3V3 for Marvel Vddio 
  - 25Mhz crystal oscillator
  - CNFG0,1,2 setup
  - T0,1,2,3,4,5,6,7,8 setup
  - will require 3V3 and ground solder points from all six motherboard revisions
    - 1.0 , 1.1 , 1.2 , 1.3 , 1.4 , 1.6/b

- xbox motherboard IDE socket
- DVD drive IDE header
- SATA to HDD/SATA socket

Desirables
==========
- Marvell 88SA8052 datasheet
- Connect pcb directly to xbox ide header on motherboard.
- Use motherboard 3V3 reducing one power regulator.
- Use existing IDE cable from pcb to dvd drive.
  - Cut or roll second connector behind dvd drive.
- Use power from existing molex connector to HDD/SSD.
  
Software used
=============
- GIMP 2.99.18 development release
- KiCad Schematic Editor 8.0.1
- Proteus 8.15 SP1
  
Sources
=======
- https://www.psdevwiki.com/ps3/88SA8040-TBC1
- https://consolemods.org/wiki/Xbox:Versions
- https://www.ioi.com.tw/products/proddetail.aspx?CatID=101&HostID=2010&DeviceID=3002&ProdID=1010114
- https://en.wikipedia.org/wiki/Parallel_ATA
- https://www.startech.com/en-gb/hdd/ide2sat2

