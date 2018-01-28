# Assembly

A few important notes before we begin.
 - This is a soldered, sandwich-case design. Unlike other sandwich designs with screws and standoffs, you cannot disassemble this keyboard. Flash the pro micros and check each swich socket with a paperclip before you solder the switches in. Check that the RGB layer works by putting the PCB in place and pushing the RGB pins to the side. If you are done and one of your diodes is in the wrong direction or a pad on an LED wasn't soldered, you can't go back.
 - When using the keyboard, be careful to not remove or connect the TRRS cable while the board is plugged in. The RGB LEDs are sensitive, and there isn't really a way to avoid having the contacts within the 3.5mm connector brush against the plug.
 - The RGB LEDs pull a lot of power. So much so, that if you set the color to white by reducing saturation, the voltage to the right arduino will drop too low and it will fail. If this happens, simply unplug the USB, then the right half, and set the saturation back up with the left half only. If you really want white backlighting, you will need to set the brightness down.
 - [**Watch this video**](https://www.youtube.com/watch?v=_DsCdOaRUPM&feature=youtu.be)
 

## Parts

If you are just building one half, you don't need a TRRS jack or cable.

**Included in the kit**
- [ ] Set of PCBs. Top, middle, and bottom are standard. Bases are extra.

![](https://i.imgur.com/7u5cPOM.png)

- [ ] **2** TRRS jacks ([CP-43514-ND](https://www.digikey.com/product-detail/en/cui-inc/SJ-43514/CP-43514-ND/368146))
- [ ] **62** 1N4148w diodes
- [ ] **32** 100NF 0805 capacitors
- [ ] **32** SK6812 or WS2812b RGB LEDs
- [ ] **14** 3x1 Pin connectors. The kit includes **2** 40x1 rows, break them into 3x1 sections.


**Not included in the kit**
- [ ] **2** 5V/16MHz Pro Micros with pins ([official](https://www.sparkfun.com/products/12640) or [clone](https://smile.amazon.com/s/ref=nb_sb_ss_i_2_10?url=search-alias%3Daps&field-keywords=pro+micro+arduino&sprefix=pro+micro+%2Caps%2C352&crid=3CHDJYMGX12DJ))
- [ ] **4** [2u PCB-mount stabilizers](https://1upkeyboards.com/clear-cherry-pcb-mount-stabilizers.html) Transparent stabilizers work best. The case does not support plate-mount stabs.
- [ ] **62** Switches. The PCB is alps-compatible but the top plate is not. For best RGB effects, get switches with transparent housings like Zealios, Cherry RGB, or Outemu ice.
- [ ] [TRRS cable](https://www.amazon.com/gp/product/B019TRW4HQ/ref=oh_aui_detailpage_o04_s00?ie=UTF8&psc=1)
- [ ] [Bumper feet  of your choice](https://www.amazon.com/gp/product/B01HJ64HHO/ref=oh_aui_detailpage_o00_s01?ie=UTF8&psc=1) or [rubber sheet (12"x12"](https://www.mcmaster.com/#1374n21/=1b9bcs9)

## Build overview

 1. Solder Diodes, Pro Micro, and TRRS jack to the middle plate
 2. Solder LEDs and capacitors to bottom plate
 3. Program pro micros and test both boards
 4. Solder top plate, switches, pins, and middle plate together
 5. Finish soldering with the bottom and optional base plates

## Middle PCB


Let's start with the middle plate. This is the smallest one with the rectangular holes in it. This PCB will hold the diodes, pro micro, trrs jack, and eventually, the switches.

![](https://i.imgur.com/vCnyORq.jpg)

The diodes need to be soldered to the top side of the PCB, the same as the Pro Micro and TRRS Jack. There is a set of lines around each of the diode pads. The diodes will be soldered so that the line on the diode connects with the lines at the bottom, like shown in the second image below. The diodes' marking is very light, so be careful which direction they are going.

![](https://i.imgur.com/1fvQm33.jpg)
![](https://i.imgur.com/v3tLdsz.png)

First, put some solder on half the pads. You don't need that much, the "bubble" of solder should be smaller than a half sphere. If it looks like more than a half sphere, you've used too much. Check the image below for a good idea of how much solder should be there. 

![](https://i.imgur.com/fcO9RJa.jpg)

Then, using the same method as the video above, heat the solder and place the diode in using the tweezers. You can push down on the diode with the tweezers and reheat the solder to make sure the diode lays flat on the PCB. Then, solder the other pad and you're done.

Next, we're going to attach the Pro Micro. Unlike other split builds (Lets_Split, Nyquist, Iris), the pro micro and TRRS jack are mounted to the top of the PCB. On the left side, the components of the Pro Micro are "up" and sits flush with the main PCB. On the right side, the components are "down" and the spacers included on the pins are used. There's some text on the PCB to remind you. You can solder the pins to the board or the pro micro first, whatever you prefer.

> *Tip:* Don't use too much solder, or the bottom plate won't fit on. Heat the pin with the soldering iron and touch the solder wire to the base of the pin.

On the left side, once everything is soldered, you can cut the plastic part of the pin connectors with flush cutters into smaller sections and remove it. Then trim the pins on both sides, like shown below. Save 2 of the cut pins.

![](https://i.imgur.com/NIzh2oF.jpg)
![](https://i.imgur.com/5sPN8j5.jpg)

Next, using the two pins, connect the jumpers as shown below, following the indicator lines. You can use the same SMD soldering technique.

![](https://i.imgur.com/4cbS4Tu.jpg?1)

Finally, solder the 3.5mm TRRS jack onto the same side as the Pro Micro. 

## Bottom PCB

![](https://i.imgur.com/3Diajqw.jpg)

The bottom PCB is used for the RGB LEDs and capacitors. Using the same method as the diodes, solder the capacitors and LEDs onto the PCB. Capacitor direction doesn't matter, but the LED's corner mark must line up with the one printed on the board. All of the LEDs are oriented in the same direction.

![](https://i.imgur.com/8W6Q0b7.jpg)

## Testing

Now is a good time to test both boards before we solder the switches on. Skip ahead to flashing and program the board. You can test the keys by jumping the contacts with the tweezers or a paperclip. Then, place the bottom plate under the middle plate and use a 3x1 pin connector to "jump" the contacts closest to the TRRS jack. If the lights don't flash on, you either need to jump the key to turn them on, or check your solder pads for the LEDs. **Do not move onto the next step until you've verified that the switch contacts and LEDs work.**

## Solder the pins and switches

Install the 3x1 pins into the middle plate. If you have an extra bottom plate, make sure the longer legs are facing down. The R1.1 will only have a solder pad on the middle, so just solder the center pin for now. For the 3 pins closest to the 3.5mm jack, solder all of the contacts. Then trim the tops of the pins.

![](https://i.imgur.com/ocXjHjr.jpg)

Next, place the switches into the top plate in the layout you want. The top plate supports 1u and 1.5u switch positions. Install your 2u stabiliers. Check that all the pins on the switches are straight and secure the top to the middle PCB. You will have to use some force to push the switches all the way into the PCB. Then, once all the switches are pushed down all the way, you can solder the switches in.

## Final assembly

Once the switches are all soldered in, put the bottom plate over with the LEDs sitting inside the rectangular holes. Solder the two remaining pins for the rest of the board, and all 3 for the RGB pins. 

![](https://i.imgur.com/yWuU0Hx.jpg)

----------------------------------------------------------------------------------------------------