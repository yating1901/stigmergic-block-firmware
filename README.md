Firmware and Bootloader for the Stigmergic Block (Yatings version)
==============

This repository contains the firmware and bootloader for the stigmergic block. The code uses AVR Libc and is based on the Arduino AVR core libraries. In many cases, the Arduino libraries have been significantly modified and only some parts of the code base still resemble the [original code](https://github.com/arduino/ArduinoCore-avr).

## Useful commands
1. Upload the bootloader
```bash
avrdude -c buspirate -p m328p -P /dev/ttyUSBX -U lock:w:0x3F:m -U lfuse:w:0xFF:m -U hfuse:w:0xDE:m -U efuse:w:0x05:m -U flash:w:optiboot_atmega328.hex -U lock:w:0x0F:m
```

2. Upload the firmware
```bash
avrdude -c arduino -p m328p -P /dev/ttyUSBX -b 57600 -U flash:w:firmware.hex
```
