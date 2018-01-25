# Assembly

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->


- [Parts](#parts)
- [SMD Soldering](#SMD-Soldering)
- [Mount the TRRS Jack](#mount-the-trrs-jack)
- [Connect Jumpers](#connect-jumpers)
- [I2C Resistors and Jumpers](#i2c-resistors-and-jumpers)
  - [Mount the resistors](#mount-the-resistors)
  - [Connect the I2C Jumpers](#connect-the-i2c-jumpers)
- [Mount Header Pins](#mount-header-pins)
- [Mount the Pro Micro](#mount-the-pro-micro)
  - [Mount the 2 switches under the Pro Micro](#mount-the-2-switches-under-the-pro-micro)
  - [Mount the Pro Micro the Right Way](#mount-the-pro-micro-the-right-way)
- [Mount the rest of the switches](#mount-the-rest-of-the-switches)
- [Assemble the case](#assemble-the-case)
- [Finishing touches](#finishing-touches)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->


## Parts

If you are just building one half, you don't need a TRRS jack or cable.

**Included in the kit**
- [ ] Set of PCBs. Top, middle, and bottom are standard. Bases are extra.
- [ ] **2** TRRS jacks ([CP-43514-ND](https://www.digikey.com/product-detail/en/cui-inc/SJ-43514/CP-43514-ND/368146))
- [ ] **62** 1N4148w diodes
- [ ] **32** 100NF 0805 capacitors
- [ ] **32** SK6812 or WS2812b RGB LEDs


**Not included in the kit**
- [ ] **2** 5V/16MHz Pro Micros with pins ([official](https://www.sparkfun.com/products/12640) or [clone](https://www.ebay.com/sch/i.html?_from=R40&_sacat=0&_nkw=Arduino+Micro+Pro+ATmega32U4+5V&rt=nc&LH_BIN=1))
- [ ] **4** [2u PCB-mount stabilizers](https://1upkeyboards.com/clear-cherry-pcb-mount-stabilizers.html)
- [ ] **62** Switches. The PCB is alps-compatible but the top plate is not. For best RGB effects, get switches with transparent housings like Zealios, Cherry RGB, or Outemu ice.
- [ ] [TRRS cable](https://www.amazon.com/gp/product/B019TRW4HQ/ref=oh_aui_detailpage_o04_s00?ie=UTF8&psc=1)
- [ ] [Bumper feet or rubber sheet of your choice](https://www.amazon.com/gp/product/B01HJ64HHO/ref=oh_aui_detailpage_o00_s01?ie=UTF8&psc=1)


## SMD Soldering

Diodes allow current to flow in one direction only. Mount the diodes with the black line facing the square pad.

![]()

You'll want to determine the orientation of your boards right now. Remember, they're symmetrical, but you can set it up to have your TRRS jacks on the inside or on the same side (right or left). For this build we'll be mounting our TRRS jacks on the inside, closest to one another.

- The **left PCB** will have the **TRRS jack on the right**
- The **right PCB** will have the **TRRS jack on the left**

This orientation will determine the top of your PCB. Insert the diodes on the top. Once mounted they will fit between the PCB and the plate.

> *Tip:* Although it doesn't actually matter which side you mount the diodes on so long as they're in the correct orientation, there are several factors that may influence which side you choose. If you have a 3mm acrylic plate, it is desirable to mount them on the top side to help reinforce the gap and prevent the switches from rising up with the PCB. If you have a 5mm acrylic plate, it is mandatory to mount them on the bottom side for the plate to fit. If it is left up to choice, it can be beneficial to mount them on the bottom side to allow for future desoldering replacement should there be some type of failure. For this build we'll put them on top.

Use a helping hand tool to hold the PCB above your work surface.

Use a small book binding or small pair of pliers to gently make a 90 degree bend on each side of the diode. It might take a few tries to get right, but you'll get the hang of it soon. They should drop easily into the 2 holes.

**Double check your work**. Black lines should be facing the square pad.

> *Tip:* **Lightly** tack each diode in from the top. This will keep them snug against the surface once we flip it over and do the real soldering from the bottom. You only need a tiny amount of solder here and you should still be able to see through the hole.

Flip your PCB over and solder the diodes then snip the excess leads.

## Mount the TRRS Jack

Mount the TRRS jack on the side opposite from your diodes. It should be on the bottom.

> *Tip:* Use masking tape or a spare finger to hold it in place while you solder it. Tack a couple pins and make sure it's snug against the board, then do the rest.

## Connect Jumpers

On the **underside** of the PCB, right below the TRRS jack, you'll see two sets of 3 pads labelled VCC and GND. Jumper them like this:

```
VCC [x]     [ ] VCC
    [x]     [x]
GND [ ]     [x] GND
```

Do both PCBs the same.

![](http://i.imgur.com/eLRUJxA.jpg)

## I2C Resistors and Jumpers

*Optional if you plan to use I2C.*

### Mount the resistors

On one PCB, mount and solder two 4.7kΩ resistors, one in each of the spaces labeled "R" on the same side of the PCB as you mounted the diodes. Resistors are not polarized and can be mounted in either direction.

*Note: It doesn't matter which PCB ends up with the resistors. It's OK, but unnecessary, to place them on both.*

### Connect the I2C Jumpers

On the **underside** of the PCB, you'll find the I2C jumper pads located below the D17 diode. Jumper the pads on both PCBs.

## Mount Header Pins

You should have received header pins with your Pro Micro. Insert the short side into the bottom of PCB (same side as the TRRS jack) and solder them in.

> *Tip:* To keep them aligned you can slip the Pro Micro over the pins but **do not solder the Pro Micro at this time**.

Tack the pins on the end and inspect. If the pins are not quite aligned with the board, heat one side with your iron and press it in. It should make a satisfactory "click".

Solder the rest of the pins (it won't take much solder here).

The long part of the pins should be protruding from the bottom. We'll trim these later after soldering the Pro Micro, but you can leave them be for now.

## Mount the Pro Micro

**Pay special attention on this step**. There are several things that need to be done in the right order and orientation.

> *Tip:* Flash your Pro Micro now before you mount it. You can test it by using a multimeter to measure the voltage between VCC and RAW. It should be around 5V. If it's bad it'll be a lot less headache than desoldering.

### Mount the 2 switches under the Pro Micro

> *Heads up:* The plate design linked in this build is not symmetrical. One edge is slightly smaller than the other. You probably want the small edge towards the center of the board.

1. Grab 2 switches and your top plate (That's 2 switches for each side)
2. Snap the switches into your plate in the spots that overlay the Pro Micro (on the left side that's column 2, and on the right that's column 5).
3. Line up your PCB with the switches and solder them between the header pins

### Mount the Pro Micro the Right Way

You'll be working from the bottom of the board for this step.

- On the **left PCB** the Pro Micro should be **smooth side up** (facing you)
- On the **right PCB** the Pro Micro should be **component side up** (facing you)

![](http://i.imgur.com/r4kMBSF.jpg)

You may need to **trim the pins on the left side switches** as they will likely touch the controller and prevent it from resting flush with the pins.

**Clearance is going to be tight on the right side** between the USB and the bottom of the plate, so make sure you've got it as snug as possible against the header pins.

Ensure the orientation of your controllers are correct and you've already soldered the 2 switches underneath, then solder all the pins on the Pro Micro.

At this point you should be able to plug in and verify the board is working and the two mounted switches should work (if you already flashed). If it is, great job!

Trim the excess from the header pins.

![](http://i.imgur.com/WOOB0nr.jpg)

## Mount the rest of the switches

Home stretch. Gently snap in the rest of the switches and solder them.

![](http://i.imgur.com/GFF0sd7.jpg)

## Assemble the case

1. Insert the screws on top
2. Screw the standoffs onto the top screws
3. Line up the bottom of the case with the standoffs
4. Screw in the bottom screws to the standoffs

![](http://i.imgur.com/coW4MsQ.jpg)
> *Tip:* Finger tight is sufficient, but you can snug them down just a tad with a tool. Be easy, they don't need much!

## Finishing touches

1. Add some adhesive vinyl pads to the bottom
2. Install your keycaps and connect the two halves with the TRRS cable.

You did it! Great job!

