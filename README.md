# LS-3A6000 Overclock BIOS

## Introduction

These BIOS firmware patched the `PLL(0x1fe001b0)` configuration and adjust the `Main Clock` parameters in PreSecMain module, which slightly increase the CPU frequency.

Detailed blog can be found at https://naivekun.com/2023/12/loongson-3a6000-overclock/

|      File name      |Main Clock|CPU Clock|HTcore Clock|
|---------|----------|---------|---------|
|bios_backup.bin|2500Mhz|2500Mhz|1250Mhz|
|bios_boost2600.bin|2600Mhz|2600Mhz|975Mhz|
|bios_boost2700.bin|2700Mhz|2700Mhz|1012.5Mhz|

## Usage

1. Format a USB drive with FAT32 partition
2. Copy BIOS firmware to the USB drive
3. Insert your USB drive, power on motherboard
4. Enter BIOS setup, select `Security-Firmware Update`, and select the firmware you desire to flash
5. Hit enter and wait 2-3 minutes
