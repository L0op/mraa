UP Squared  Board   {#up2}
================================
UP Squared is based on the Intel&reg; Celeron&trade; N3350 or the Intel&reg; Pentium&trade; N4200, formerly Skylake&trade;.

For the full specification please refer to the main specification page here:

http://www.up-board.org/upsquared/specifications-up2

Interface notes
-----------------------
The Up Squared present one Raspberry Pi compatible HAT connector and a  60 pin exHAT connector. Currently this implementation only support the interfaces through the HAT connector.

**I2C**
 - 2 channels
 - support: standard-mode (100kHz), fast-mode (400kHz) , Fast-mode plus (1MHz), High-speed mode (3.4MHz)
 - bus frequency can be selected in BIOS settings.
 - the default i2c channel is the one connected to the pin 3,5 of the hat

**SPI**
- Bus frequencies up to 10MHz are supported.
- 3 chip-selects.

**PWM**
 - up to 3 channel of PWM

**UART**
- 1 high-speed UART is available
- supporting baud rates up to 3686400 baud.
- Hardware flow-control signals are available on pins 11/36 (RTS/CTS).

Please note that a kernel with UP board support is required to enable the I/O
interfaces above.

Refer to http://www.up-community.org for more information.

Pin Mapping
--------------------
The GPIO numbering in the following pin mapping is based on the Raspberry Pi
model 2 and B+ numbering scheme.

NOTE: the i2c device numbering depend on various factor and cannot be trusted:
the right way of determining i2c (and other devices) numbering is through PCI
physical device names. See the source code in src/x86/up2.c for details.

| MRAA no. | Function     | Rpi GPIO   | Sysfs GPIO | Notes                          |
|----------|--------------|------------|------------|--------------------------------|
| 1        | 3V3 VCC      |            |            |                                |
| 2        | 5V VCC       |            |            |                                |
| 3        | I2C1_SDA     | 2          | 462        | I2C1 (/dev/i2c-1)              |
| 4        | 5V VCC       |            |            |                                |
| 5        | I2C1_SCL     | 3          | 463        | I2C1 (/dev/i2c-1)              |
| 6        | GND          |            |            |                                |
| 7        | GPIO(4)      | 4          | 433        |                                |
| 8        | UART1_TX     | 14         | 477        | UART1 (/dev/ttyS1)             |
| 9        | GND          |            |            |                                |
| 10       | UART1_RX     | 15         | 476        | UART1 (/dev/ttyS1)             |
| 11       | UART1_RTS    | 17         | 478        |                                |
| 12       | I2S_CLK      | 18         | 326        | I2S0 (PCM Audio)               |
| 13       | GPIO(27)     | 27         | 432        |                                |
| 14       | GND          |            |            |                                |
| 15       | GPIO(22)     | 22         | 431        |                                |
| 16       | PWM3         | 23         | 471        | PWM Chip 0 Channel 4           |
| 17       | 3V3 VCC      |            |            |                                |
| 18       | GPIO(24)     | 24         | 405        |                                |
| 19       | SPI0_MOSI    | 10         | 422        | SPI2 (/dev/spidev1.x)          |
| 20       | GND          |            |            |                                |
| 21       | SPI0_MISO    | 9          | 421        | SPI2 (/dev/spidev1.x)          |
| 22       | GPIO(25)     | 25         | 402        |                                |
| 23       | SPI0_SCL     | 11         | 418        | SPI2 (/dev/spidev1.x)          |
| 24       | SPI0_CS0     | 8          | 419        | SPI2 (/dev/spidev1.0)          |
| 25       | GND          |            |            |                                |
| 26       | SPI0_CS1     | 7          | 420        | SPI2 (/dev/spidev1.1)          |
| 27       | I2C0_SDA     | 0          | 464        | I2C0 (/dev/i2c-0)              |
| 28       | I2C0_SCL     | 1          | 465        | I2C0 (/dev/i2c-0)              |
| 29       | GPIO(5)      | 5          | 430        |                                |
| 30       | GND          |            |            |                                |
| 31       | GPIO(6)      | 6          | 404        |                                |
| 32       | PWM0         | 12         | 468        | PWM Chip 0 Channel 0           |
| 33       | PWM1         | 13         | 469        | PWM Chip 1 Channel 0           |
| 34       | GND          |            |            |                                |
| 35       | I2S_FRM      | 19         | 327        | I2S0 (PCM Audio)               |
| 36       | UART1_CTS    | 16         | 479        |                                |
| 37       | GPIO(26)     | 26         | 403        |                                |
| 38       | I2S_DIN      | 20         | 328        | I2S0 (PCM Audio)               |
| 39       | GND          |            |            |                                |
| 40       | I2S_DOUT     | 21         | 329        | I2S0 (PCM Audio)               |