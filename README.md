
![svlinky-logo](logo/svlinky-alt-color-blue-high-resolution-logo-black-on-white.png)

# SVLINKY
##  Summary

Pro Micro footprint with USB-C, RP2040, and a [VIK](https://github.com/sadekbaroudi/vik) connector

![svlinky photo](pcb/doc/svlinky_photo.jpg?raw=true "svlinky")

## Features

 * Pro-micro / Sparkfun RP2040 compatible footprint, with VIK connector on the bottom
 * Raspberry Pi RP2040 MCU
 * Up to 16MB flash memory _(depending on component selection and availability)_
 * USB VBUS detect
 * Low profile USB-C mid-mount connector
 * Designed to be manufactured and assembled by all common PCBA services (including JLCPCB)

## Pinout

The pinout is compatible with the widely available [SparkFun RP2040](https://www.sparkfun.com/products/18288), but has almost all the additional GPIO from the RP2040 broken out to the VIK connector on the bottom of the controller.

USB VBUS detection on GPIO19.

TODO: put together detailed pinout with reference images

## Programming

In order to put the board in bootloader mode, quickly short the RESET and ground pins (marked **R** and **GND**) while shorting the two through holes on the bottom half of the controller on the top side.

TODO: add image showing pcb spots

Note: If mounting the controller with components face down, you will lose access to the BOOT through holes. Before mounting the controller, you can solder short wires to these through holes so you can access them. This is only necessary if you can't trigger the bootloader by shorting the RESET and GND pins. The likelihood is that you'll never need to do the BOOT method if using this for a mechanical keyboard running QMK, for example.

## Firmware

As of this writing (2023-09-14), I have written and tested firmware for the SVLINKY using QMK and a collection of VIK modules.

You can use this as a reference:
https://github.com/sadekbaroudi/qmk_firmware/tree/develop_fingerpunch/keyboards/fingerpunch/svlinky

This QMK firmware has everything mapped out such that you can copy it as a starting point, and modify/add/remove pin mappings based on the board that you are connecting the SVLINKY to.

At some point, I'd also like to add a SVLINKY converter using the [QMK converters](https://github.com/qmk/qmk_firmware/blob/master/docs/feature_converters.md) framework.

## Manufacturing

To manufacture the SVLINKY, you can use the files in the [pcb/production](./pcb/production/) directory.

*Note: The following instructions are based on JLCPCB's order flow, but is subject to change*

Instructions for [JLCPCB](https://jlcpcb.com)
* gerbers - upload these from the main PCB screen
  * Be sure to PCB Assembly
  * For PCBA type, select Standard
  * For Assembly Side, select Both Sides
  * Click Confirm
* Click next until you get to the bill of materials
* Upload both the bom.csv and the positions.csv (found in the gerber.zip file)
* Double check that all the components are placed appropriately
* Order!

## Credits

Special thanks to:

 * **plut0nium for creating the splinky. I used that as a base for this controller.**
 * pyntiehet for coming up with the name
 * jasonhazel, AlaaSaadAbdo, deltawhy, yingeling, bom, ridingintraffic, and the rest of the fingerpunch discord server for always being there to give great input and suggestions!