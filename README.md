[![MCHP](images/microchip.png)](https://www.microchip.com)

# PIC18F47Q10 Exchanging Data as a Client SPI Device Using Interrupts

## Objective
This repository contains an example of Foundation Services generated source code for SPI as described in [*TB3265 - Getting Started with SPI using MSSP on PIC18*](https://www.microchip.com/wwwappnotes/appnotes.aspx?appnote=en1002275) document from Microchip.
<br>In this demo, the SPI will be configured as client and it will be used to exchange data. The data transfer is triggered by interrupts.

## Related Documentation
- [TB3265 - Getting Started with SPI using MSSP on PIC18](https://www.microchip.com/wwwappnotes/appnotes.aspx?appnote=en1002275)
- [PIC18-Q10 Product Family Page](https://www.microchip.com/design-centers/8-bit/pic-mcus/device-selection/pic18f-q10-product-family)
- [PIC18F47Q10 Data Sheet](http://ww1.microchip.com/downloads/en/DeviceDoc/40002043D.pdf)
- [PIC18F47Q10 Code Examples on GitHub](https://github.com/microchip-pic-avr-examples?q=pic18f47q10-cnano&type=&language=)

## Software Used
- MPLAB® X IDE 5.30 or newer [(microchip.com/mplab/mplab-x-ide)](http://www.microchip.com/mplab/mplab-x-ide)
- MPLAB® XC8 2.10 or a newer compiler [(microchip.com/mplab/compilers)](http://www.microchip.com/mplab/compilers)
- MPLAB® Code Configurator (MCC) 3.95.0 or newer [(microchip.com/mplab/mplab-code-configurator)](https://www.microchip.com/mplab/mplab-code-configurator)
- MPLAB® Code Configurator (MCC) Device Libraries PIC10 / PIC12 / PIC16 / PIC18 MCUs 1.79.0 or newer [(microchip.com/mplab/mplab-code-configurator)](https://www.microchip.com/mplab/mplab-code-configurator)
- MPLAB® Code Configurator (MCC) Foundation Services Library [(microchip.com/mplab/mplab-code-configurator)](https://www.microchip.com/mplab/mplab-code-configurator)
- Microchip PIC18F-Q Series Device Support 1.3.89 or newer [(packs.download.microchip.com/)](https://packs.download.microchip.com/)

## Hardware Used
- PIC18F47Q10 Curiosity Nano [(DM182029)](https://www.microchip.com/Developmenttools/ProductDetails/DM182029)

## Setup
The PIC18F47Q10 Curiosity Nano Development Board is used as the test platform.

<br><img src="images/PIC18F47Q10_CNANO.png" width="600">

The following configurations must be made for this project:
- Clock
  - Oscillator Select: HFINTOSC
  - HF Internal Clock: 64 MHz
  - Clock Divider: 1
- MSSP1:
  - MSSP1 Enabled
  - MSSP1 Interrupts Enabled
  - Serial Protocol: SPI
  - Mode: Client
  - Data Mode: 0

- Watchdog Timer: disabled
- Low-voltage Programming: enabled

|Pin           | Configuration      |
| :----------: | :----------------: |
|RA5 (SS)      | Digital Input      |
|RC3 (SCK)     | Digital Input      |
|RC4 (SDI)     | Digital Input      |
|RC5 (SDO)     | Digital Output     |

## Operation
1. Connect the board to the PC.

2. Open the *pic18f47q10-cnano-spi-client-int-fs.X* project in MPLAB® X IDE.

3. Set *pic18f47q10-cnano-spi-client-int-fs.X* project as main project. Right click on the project in the *Projects* tab and click *Set as Main Project*.

4. Select the *PIC18F47Q10 Curiosity Nano* in the *Hardware Tool* section of the project settings:
  - Right click on the project and click *Properties*;
  - Select the *PIC18F47Q10 Curiosity Nano* (click on the SN) in the *Hardware Tool* tab and then click *OK*:
<br><img src="images/SPI-client-int-fs-tool.PNG" width="600">


5. Program the project to the board: right click on the project and click *Make and Program Device*.

Result:
- Channel 0 -> SCK
- Channel 1 -> Client SDI/Host SDO
- Channel 2 -> Client SDO/Host SDI
- Channel 3 -> SS1
- Channel 4 -> SS2 (for other client device)
<br><img src="images/client-receive.png" width="600">


## Summary
This project is an illustration for a basic use case based around MSSP1 in SPI mode.
