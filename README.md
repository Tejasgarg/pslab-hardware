# PSLab-Mini-hardware

[![PSLab-Hardware](https://github.com/fossasia/pslab-hardware/actions/workflows/hardware-ci.yml/badge.svg)](https://github.com/fossasia/pslab-hardware/actions/workflows/hardware-ci.yml)
[![Gitter](https://badges.gitter.im/fossasia/pslab.svg)](https://gitter.im/fossasia/pslab?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge)
[![Twitter Follow](https://img.shields.io/twitter/follow/pslabio.svg?style=social&label=Follow&maxAge=2592000?style=flat-square)](https://twitter.com/pslabio)

This branch is dedicated to prototyping PSLab-mini board and push out a working board that has functionalities of oscillscope, multimeter and if time allows it, a logic analyser.

## PCB Layout
* I made a new PCB layout by first updating and removing components from the PSLab Schematic.
* Then imported the changed schematic into a fresh PCB editor file in KiCAD.
* Made a new edge cuts that provide a smaller footprint to the board compared to the current board
* Placed all the components and made a 4 layer PCB
* The 4 layers are as following:
     * F.Cu(Front Copper) - Consists of signal routings
     * GND(Gound) - Consist of a ground pour in the entire layer
     * VDDA(Power) - Consist of a copper pour that transmits power to majority of the components
     * B.Cu(Bottom Copper) - Also consists of the routing
* Used both through and burried vias:
     * Burrried Vias - Used Buried vias for connecting the components to the gorund and power layer
     * Through Vias - Used Through vias for connecting the top and bottom copper layer for essentially connecting and routing where ever there was blockage 
       due to already present routes
       

Front Side                        | Back Side
 -------------------------------- | ----------------------------------
![Screenshot 2025-04-08 at 3 04 56 PM copy](https://github.com/user-attachments/assets/1104c163-efd1-4922-8c99-5edf4b4aa182) | ![Screenshot 2025-04-08 at 3 05 13 PM copy](https://github.com/user-attachments/assets/ab8984cb-9091-4645-85ad-bdd69faf825d)

## New Schematic
The new schematic has been made on top of the current schematic for a quiker prototype and clearly shows all the components removed in the current PSLab board and explains resoning behind removable of each. 

<img src="https://github.com/user-attachments/assets/4487f714-e261-4675-8c0c-774fbae5222c" alt="PSLab mini" width="700">


## Platform

* Microcontroller Platform : [PIC24EP256GP204](http://www.microchip.com/wwwproducts/en/PIC24EP256GP204)
* IDE: [MPLABX IDE v3.35](http://www.microchip.com/mplab/mplab-x-ide) (Supported on Linux/Windows/Mac)
* Compiler: [MPLAB® XC16 Compiler](http://www.microchip.com/mplab/compilers)
* Programming Tool: [PICkit™ 3 In-Circuit Debugger](http://www.microchip.com/Developmenttools/ProductDetails.aspx?PartNO=PG164130)

## New parts list

* [PIC24EP256GP204](http://www.microchip.com/wwwproducts/en/PIC24EP256GP204) - Microcontroller
* [MCP6S21](http://www.microchip.com/wwwproducts/en/mcp6s21) - Programmable gain amplifier
* [TL082](http://www.ti.com/product/TL082) - 2 channel Op-Amp
* [CP2102N-A02-GQFN24](https://www.silabs.com/documents/public/data-sheets/cp2102n-datasheet.pdf) - USB-UART bridge
* [SP0503BAHTG](https://m.littelfuse.com/~/media/electronics/datasheets/tvs_diode_arrays/littelfuse_tvs_diode_array_sp05_datasheet.pdf.pdf) - ESD protector

* 0.5 A Fuse
* Assorted resistors, capacitors & diodes

## Hardware Specs

* 3-Channel up to 2MSPS Oscilloscope. Software selectable amplification stages
* 12-bit Voltmeter . Input ranges from +/-10 mV to +/-16 V
* Capacitance Measurement. pF to uF range
* UART data buses for secondary modules 

## Feature list for PSLab-Mini

### Oscilloscopes

One of the main features of PSLab is the 3-channel Oscilloscope which can monitor analog inputs at maximum of 2 million samples per second.
In PSLab mini, this will be retained but with the following changes:
* Reduce the channels from 3 to 2 channel oscilloscope to reduce the components and cost
* Aim at increasing the max sampling rate

### Measurement Functions

* Frequency counter tested up to 16 MHz.
* Capacitance Measurement. pF to uF range
* Resistance measurement
* Voltmeter with a range of +/-10 mV to +/-16 V


### Other useful tools

* UART outputs
* Graphical Interfaces for Oscilloscope, Multimeter, streaming data and several experiments developed that use a common framework which drastically reduces code required to incorporate control and plotting widgets.
