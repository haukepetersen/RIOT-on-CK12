nrf52 pin map (revision H09-V01 2018010)
========================================

P0.00  ->  GPIO_PIN(0, 00)  ->  XL1 (LF crystal, 32768kHz)
P0.01  ->  GPIO_PIN(0, 01)  ->  XL2 (LF crystal, 32768kHz)
P0.02  ->  GPIO_PIN(0, 02)  ->  vibration motor
P0.03  ->  GPIO_PIN(0, 03)  ->  pad
P0.04  ->  GPIO_PIN(0, 04)  ->  ?
P0.05  ->  GPIO_PIN(0, 05)  ->  pad
P0.06  ->  GPIO_PIN(0, 06)  ->  pad
P0.07  ->  GPIO_PIN(0, 07)  ->  ?
P0.08  ->  GPIO_PIN(0, 08)  ->  ?
P0.09  ->  GPIO_PIN(0, 09)  ->  ?
P0.10  ->  GPIO_PIN(0, 10)  ->  ?
P0.11  ->  GPIO_PIN(0, 11)  ->  ?
P0.12  ->  GPIO_PIN(0, 12)  ->  ?
P0.13  ->  GPIO_PIN(0, 13)  ->  ?
P0.14  ->  GPIO_PIN(0, 14)  ->  ?
P0.15  ->  GPIO_PIN(0, 15)  ->  ?
P0.16  ->  GPIO_PIN(0, 16)  ->  ?
P0.17  ->  GPIO_PIN(0, 17)  ->  ?
P0.18  ->  GPIO_PIN(0, 18)  ->  ?
P0.19  ->  GPIO_PIN(0, 19)  ->  ?
P0.20  ->  GPIO_PIN(0, 20)  ->  ?
P0.21  ->  GPIO_PIN(0, 21)  ->  ?
P0.22  ->  GPIO_PIN(0, 22)  ->  ?
P0.23  ->  GPIO_PIN(0, 23)  ->  ?
P0.24  ->  GPIO_PIN(0, 24)  ->  ?
P0.25  ->  GPIO_PIN(0, 25)  ->  pad
P0.26  ->  GPIO_PIN(0, 26)  ->  pad
P0.27  ->  GPIO_PIN(0, 27)  ->  ?
P0.28  ->  GPIO_PIN(0, 28)  ->  ?
P0.29  ->  GPIO_PIN(0, 29)  ->  ?
P0.30  ->  GPIO_PIN(0, 30)  ->  ?
P0.31  ->  GPIO_PIN(0, 31)  ->  ?
SWCLK  ->  pad `LK3`
SWDIO  ->  pad `IO2`


Tries:
i2c:
25+26 or 26+25 can not read from addr 0x18 or 0x19
same for 3+5,3+6,5+6,6+5,5+3,6+3
