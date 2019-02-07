# Easy Z80
An easy to build Zilog Z80 based single board computer

## Introduction
My son Max asked me what does it take to build a computer, and whether he can design and build one himself. This project is our attempt to design and build a simple, easy to understand, yet capable single board computer.
It reuses the same memory paging mechanism I've implemented in Zeta SBC V2, but uses Zilog Z80 peripheral ICs to make a consistent Zilog based design.

## Specifications
* Processor: Zilog Z80 CPU (CMOS version - Z84C00)
* Memory: 512 KiB battery-backed SRAM, 512 KiB Flash ROM
* I/O:
  * Zilog Z80 CTC - Programmable timer used for periodic interrupts and (optionally) for generating UART clock
  * Zilog Z80 SIO - Dual channel serial interface, used for console and for connecting to other peripheral devices
* Bus: [RC2014](https://rc2014.co.uk/) compatible

### Jumpers, Connectors, and Switches
To be completed

### Bill of Materials - Version 1.0

[Easy Z80 project on Mouser.com](https://www.mouser.com/ProjectManager/ProjectDetail.aspx?AccessID=f16751cb33) - View and order all components except of the PCB.

[Easy Z80 project on OSH Park](https://oshpark.com/shared_projects/4onyIbSB) - View and order the PCB.

Component type     | Reference | Description                                 | Quantity | Possible sources and notes 
------------------ | --------- | ------------------------------------------- | -------- | --------------------------
PCB                |           | Easy Z80 PCB - Version 1.0                  | 1        | Refer to the [RetroBrew Computers Board Inventory](https://www.retrobrewcomputers.org/doku.php?id=boardinventory#minimal_8085_z80_single_board_computer) page for ordering information, or order from a PCB manufacturer of your choice using provided Gerber or KiCad files
Integrated Circuit | U1        | Z80 CPU, CMOS, 40 pin DIP - Z84C00xxPEG     | 1        | Mouser [692-Z84C0010PEG](https://www.mouser.com/ProductDetail/692-Z84C0010PEG)
Integrated Circuit | U2        | Z80 CTC, CMOS, 28 pin DIP - Z84C30xxPEG     | 1        | Mouser [692-Z84C3010PEG](https://www.mouser.com/ProductDetail/692-Z84C3010PEG)
Integrated Circuit | U3        | Z80 SIO/0, CMOS, 28 pin DIP - Z84C40xxPEG   | 1        | Mouser [692-Z84C4010PEG](https://www.mouser.com/ProductDetail/692-Z84C4010PEG)
Integrated Circuit | U4        | 512 KiB SRAM, 32 pin DIP - AS6C4008         | 1        | Mouser [913-AS6C4008-55PCN](https://www.mouser.com/ProductDetail/913-AS6C4008-55PCN)
Integrated Circuit | U5        | 512 KiB Flash ROM, 32 pin DIP - SST39SF040  | 1        | Mouser [804-39SF0407CPHE](https://www.mouser.com/ProductDetail/804-39SF0407CPHE)
Integrated Circuit | U6        | Microprocessor Supervisory Circuit - MAX693 | 1        | Mouser [584-ADM693ANZ](https://www.mouser.com/ProductDetail/584-ADM693ANZ)
Integrated Circuit | U7, U8    | Dual RS-232 Driver/Receiver - MAX232A       | 2        | Mouser [595-TRS232IN](https://www.mouser.com/ProductDetail/595-TRS232IN)
Integrated Circuit | U9        | Simple Programmable Logic Device - ATF16V8B | 1        | Mouser [556-AF16V8B15PU](https://www.mouser.com/ProductDetail/556-AF16V8B15PU)
Integrated Circuit | U10, U11  | 4-by-4 Register File - 74HCT670             | 2        | Mouser [595-CD74HC670E](https://www.mouser.com/ProductDetail/595-CD74HC670E)
Integrated Circuit | U12       | Dual Flip Flop - 74HCT74                    | 1        | Mouser [595-SN74HC74N](https://www.mouser.com/ProductDetail/595-SN74HC74N)
Oscillator         | QG1       | 10 MHz, CMOS oscillator, Half Can           | 1        | Mouser [774-MXO45HS-3C-10.0](https://www.mouser.com/ProductDetail/774-MXO45HS-3C-10.0)
Oscillator         | QG2       | 1.8432 MHz, CMOS oscillator, Half Can       | 1        | Mouser [774-MXO45HS-3C-1.8](https://www.mouser.com/ProductDetail/774-MXO45HS-3C-1.8)
LED                | D1        | 3 mm, green LED indicator                   | 1        | Mouser [859-LTL-4231N](https://www.mouser.com/ProductDetail/859-LTL-4231N)
Tactile Button     | SW1       | 6 mm tactile button, right angle            | 1        | Mouser [653-B3F-3152](https://www.mouser.com/ProductDetail/653-B3F-3152)
Connector          | J1        | DC Power Jack, 2mm                          | 1        | Mouser [806-KLDX-0202-A](https://www.mouser.com/ProductDetail/806-KLDX-0202-A)
Connector          | J2, J3    | Sub-D DE9M, Right Angle, PCB mount          | 2        | Mouser [806-K22X-E9P-N-99](https://www.mouser.com/ProductDetail/806-K22X-E9P-N-99)
Connector          | J4        | 2 Pin Header with Friction Lock             | 1        | Mouser [571-6404562](https://www.mouser.com/ProductDetail/571-6404562)
Pin Header         | J5 - J7   | 40x2 Pin Header, 2.54 mm Pitch, Right Angle | 1        | Mouser [571-9-103326-0](https://www.mouser.com/ProductDetail/571-9-103326-0)
Capacitor          | C1 - C23  | 0.1 uF, MLCC, 5 mm Pitch                    | 23       | Mouser [594-K104K15X7RF53H5](https://www.mouser.com/ProductDetail/594-K104K15X7RF53H5)
Capacitor          | C24       | 47 uF, 25V, Aluminum Organic Polymer        | 1        | Mouser [80-A750EK476M1EAAE40](https://www.mouser.com/ProductDetail/80-A750EK476M1EAAE40)
Resistor Array     | RR1 - RR3 | 4.7 k, bussed, 5 pin SIP                    | 3        | Mouser [652-4605X-AP1-472LF](https://www.mouser.com/ProductDetail/652-4605X-AP1-472LF)
Resistor           | R1        | 470 ohm, axial                              | 1        | Mouser [603-MFR-25FBF52-470R](https://www.mouser.com/ProductDetail/603-MFR-25FBF52-470R) 
Resistor           | R2 - R4   | 10 kohm, 1% tolerance, axial                | 3        | Mouser [603-MFR-25FRF5210K](https://www.mouser.com/ProductDetail/603-MFR-25FRF5210K)
Resistor           | R5        | 29.4 kohm, 1% tolerance, axial              | 1        | Mouser [603-MFR-25FBF52-29K4](https://www.mouser.com/ProductDetail/603-MFR-25FBF52-29K4)
Trimmer Resistor   | RV1       | 2 kohm, through hole                        | 1        | Mouser [652-3362P-1-202LF](https://www.mouser.com/ProductDetail/652-3362P-1-202LF)
IC Socket          | U1, U3    | 40 pin DIP                                  | 2        | Mouser [517-4840-6000-CP](https://www.mouser.com/ProductDetail/517-4840-6000-CP)
IC Socket          | U4, U5    | 32 pin DIP                                  | 2        | Mouser [517-4832-6000-CP](https://www.mouser.com/ProductDetail/517-4832-6000-CP)
IC Socket          | U2        | 28 pin DIP                                  | 1        | Mouser [517-4828-6000-CP](https://www.mouser.com/ProductDetail/517-4828-6000-CP)
IC Socket          | U9        | 20 pin DIP                                  | 1        | Mouser [517-4820-3000-CP](https://www.mouser.com/ProductDetail/517-4820-3000-CP)
IC Socket          | U6 - U8, U10, U11 | 16 pin DIP                          | 5        | Mouser [517-4816-3000-CP](https://www.mouser.com/ProductDetail/517-4816-3000-CP)
IC Socket          | U12       | 14 pin DIP                                  | 1        | Mouser [517-4814-3000-CP](https://www.mouser.com/ProductDetail/517-4814-3000-CP)
Oscillator Socket  | QG1, QG2  | 4 pin DIP, Half Can                         | 2        | Mouser [535-1108800](https://www.mouser.com/ProductDetail/535-1108800)
