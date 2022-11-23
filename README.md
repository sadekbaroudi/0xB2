# 0xB2 - splinky
Pro-Micro/Elite-C replacement with USB-C and RP2040.

Designed for use in custom mechanical (split) keyboards, but many other uses are possible.

## splinky - ground mod

Before you proceed, note that this is a mod of the original splinky. It was forked at v3.1, and rerouted to use expose an additional RP2040 (D24). See the image below. This has not been tested as of now (2022-11-23). If you're interested in using this, please join the [fingerpunch discord](https://fingerpunch.xyz/discord) and reach out to sadekbaroudi#1258  

If you are using the controller with this mod, note that you must be aware if the pcb supports the extra gpio. If it does, then you can solder all pins of the controller to the pcb, as you normally would. If not, you should solder all pins **except** the one with the arrow next to it in the image below (labeled D24).

![Splinky Ground Mod](pcb/doc/splinky-ground-mod.jpg?raw=true "Splinvy Ground Mod")

![Splinky v2](pcb/doc/splinky_v1_photo.jpg?raw=true "Splinvy v1")

## Features:

 * Pro-micro / Sparkfun RP2040 compatible footprint, with 5 extra pins at bottom (Elite-C style)
 * Raspberry Pi RP2040 MCU
 * Up to 16MB flash memory _(depending on component selection and availability)_
 * User LED & USB VBUS detect
 * Low profile USB-C mid-mount connector
 * Designed to be manufactured and assembled by all common PCBA services (including JLCPCB)

<!--![Splinky v2](pcb/doc/render_v2.png?raw=true "Splinky v2 Render")-->

## Pinout

The pinout is compatible with the widely available [SparkFun RP2040](https://www.sparkfun.com/products/18288), with extra GPIO12..16 pins broken out on the lower side.

USB VBUS detection on GPIO19.

> This pinout is a _de facto_ standard, established by actors of the MK community (see discussions in `#RP2040` on the bastardkb Discord server) 

Additionnaly, a user LED is tied to GPIO17, can be used for UF2 bootloader status indication, or any other purpose (or turned OFF, no annoying always-on power LED).

## Programming

The splinky uses a basic two-button reset circuitry.

In order to put the board in bootloader mode, press briefly the RESET button (marked **R**) while holding the BOOT button (the second one).
If the buttons are not reachable (soldered upside down), the /RST pad can be shorted to GND, while the two smaller BOOT pads (next to D8) are maintained shorted (v2 only).

## Manufacturing

Releases contain required information (gerbers, bom, pos) for assembly by JLCPCB.

## Releases

 * **v3** updated pinout - current release
 * **v2** first public release
 * **v1** first prototyping run

## Credits

 * Raspberry Pi Foundation
   * [RP2040 Datasheet](https://datasheets.raspberrypi.com/rp2040/rp2040-datasheet.pdf)
   * [Hardware design with RP2040](https://datasheets.raspberrypi.com/rp2040/hardware-design-with-rp2040.pdf)
 * [SparkFun Pro Micro - RP2040](https://www.sparkfun.com/products/18288)
 * [Adafruit kb2040](https://learn.adafruit.com/adafruit-kb2040)
 * [sea-picro](https://github.com/joshajohnson/sea-picro) - _similar project, I borrowed some cheaper component references ^^_
 * ...
