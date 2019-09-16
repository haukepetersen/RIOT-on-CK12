# RIOT-on-CK12
Material, documentation, and progress of porting RIOT to the CK12 smartwatch


## Background
The CK12 is a one-of-many smartwatch based on Nordics nRF52832 micro-controller, providing interesting features like BLE, ECG heart rate monitoring, a Bosch BMA253 accelerometer, and a black-and-white OLED screen.

Due to its mechanical 'openness' (screws only, no glue), it promises to be a very nice playground for experimentation and other projects.

Our goal is to port [RIOT](http://www.github.com/RIOT-OS/RIOT) to the CK12


## Progress
06/20/2019 - just started
09/16/2019 - connected Debugger and flashed RIOT -> base system incl. shell over RTT is working
09/16/2019 - started to reverse engineer the pin mapping, see pinmap.md

## Code
The RIOT branch containing the WIP code can be found here:
https://github.com/haukepetersen/RIOT/tree/add_ck12

## Flashing RIOT
 As a programmer I am using a Segger JLink EDU device (https://www.segger.com/products/debug-probes/j-link/models/j-link-edu/). I guess any SWD capable programmer should do (including those cheap ST-Link clones). But for working with RIOT a JLink device is suited best, as these support Segger's `Real Time Transfer (RTT)` protocol. This enables us to run the RIOT shell over this RTT interface, without the need of any additional pins and any USB-to-serial adapter.

 Flashing the CK12 turned out to be quite simple:
 - connect the SWDIO, SWCLK, and GND pins of the JLink programmer to the pads exposed on the back of the CK12, See https://github.com/haukepetersen/RIOT-on-CK12/blob/master/images/back_swd.jpg
 - go to any RIOT application (make sure you have the `add_ck12` branch included), and flash using `BOARD=ck12 make flash`
 - connect to the RIOT shell by calling `BAORD=ck12 make term`. This will connect your host to the RIOT shell via RTT

## Special Thanks
- Curt (@curtpw) provides some basic information on the used sensor devices and pin layout in his [nRF5x-device-reverse-engineering](https://github.com/curtpw/nRF5x-device-reverse-engineering) repo, nice job!
