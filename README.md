# LS-3A6000 Overclock BIOS

## Introduction

These BIOS firmware modded two modules

* XA61200OverclockPeim
* XA61200OverclockShellCommand

the `XA61200OverclockPeim` module execute in early PEI stage and read overclock settings from EFI Variable. If EFI Variable `LsOcConf` is valid and overclock is enabled, CPU core voltage and Main Clock frequency will be set here.

the `XA61200OverclockShellCommand` register a `overclock` command in EFI shell, provide command options below

```
# print current overclock settings
Shell> overclock -p
Overclock status: ENABLE
Overclock frequency: 2700 Mhz
Overclock voltageCore: 1200 mV
Overclock voltageSA: 1100 mV

# enable overclock
Shell> overclock -e 1

# disable overclock
Shell> overclock -e 0

# set overclock frequency (Mhz)
Shell> overclock -f 2700

# set overclock core voltage (mV)
Shell> overclock -vcore 1200

# set overclock sa voltage (mV)
Shell> overclock -vsa 1100
```

## Files

* `Loongson-XA61200-UDK2018-V4.0.05494-stable202305-overclock-sa.bin`: This BIOS included overclock modding and support sa voltage adjustment
* `Loongson-XA61200-UDK2018-V4.0.05494-stable202305-overclock.bin`: This BIOS included overclock modding, only support core voltage adjustment
* `Loongson-XA61200-UDK2018-V4.0.05494-stable202305.bin`: This BIOS is the original backup of my board

## Usage

0. backup your BIOS via SPI Flash Programmer
1. Format a USB drive with FAT32 partition
2. Copy BIOS firmware to the USB drive
3. Insert your USB drive, power on motherboard
4. Enter BIOS setup, select `Security-Firmware Update`, and select the firmware you desire to flash
5. Hit enter and wait 2-3 minutes
