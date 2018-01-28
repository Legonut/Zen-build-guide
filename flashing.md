# Flashing (WIP, don't mind that it's stolen from Lets_Split)

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->


- [Which side do I flash?](#which-side-do-i-flash)
- [Windows](#windows)
- [OSX, Linux](#osx-linux)
  - [Bootloader](#bootloader)
  - [Flash](#flash)
- [Troubleshooting](#troubleshooting)
  - [Programmer not responding](#programmer-not-responding)
  - [Can't open device](#cant-open-device)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Which side do I flash?

See the QMK firmware section on [Flashing](https://github.com/qmk/qmk_firmware/tree/master/keyboards/lets_split#flashing) for an up to date explanation.

## Windows

See [/u/CampAsAChamp's Windows Guide](https://github.com/CampAsAChamp/LetsSplitWindowsGuide)

## OSX, Linux

### Bootloader

Connect RST and GND to enter bootloader. If you're using an official Sparkfun Pro Micro (the red one) you need to short this twice quickly.

You will have 8 seconds to flash before it continues on to the sketch.

> Tip: If this is the first time the Pro Micro has been flashed it should go directly to the bootloader on start.

### Flash

QMK now includes a very easy way to automatically find the serial port and flash without having to race the bootloader. From the qmk directory type:

```
make lets_split/rev2:YOUR_KEYMAP_NAME:avrdude
```

or for the Kailh hotswap socket version:

```
make lets_split/sockets:YOUR_KEYMAP_NAME:avrdude
```

Be sure to replace `YOUR_KEYMAP_NAME` with the name of your keymap.

Example:

```bash
$ make lets_split/rev2:YOUR_KEYMAP_NAME:avrdude
Reset your Pro Micro now

Connecting to programmer: .
Found programmer: Id = "CATERIN"; type = S
    Software Version = 1.0; No Hardware Version given.
Programmer supports auto addr increment.
Programmer supports buffered memory access with buffersize=128 bytes.

# [snip]

avrdude: verifying ...
avrdude: 22286 bytes of flash verified

avrdude: safemode: Fuses OK (E:CB, H:D8, L:FF)

avrdude done.  Thank you.
```

## Troubleshooting

### Programmer not responding

The controller isn't in bootloader mode. You may have missed the 8 second window to flash.
**NOTE** Power cycling doesn't work, you have to reset it with the reset pin

### Can't open device

The serial port you specified isn't the one the controller is using.