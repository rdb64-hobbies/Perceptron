Perceptron Build Guide
===========================

This guide will walk you through building a Perceptron. For more information about the Perceptron and this project, see the [README file](README.md). The only required skill is basic soldering of simple through-hole components to printed circuit boards (PCBs). Bonus if you have a 3D printer to make it look nice.

The outline of the build process is as follows:

1. Obtain the PCBs.
2. Obtain all of the other components.
3. Solder the components to the PCBs.
4. Connect the battery holders and meter and ribbon cable.
5. (Optional) Build frames.

The last step is optional for those who want to make it look nice. You'll need a 3D printer. Without this step, your Perceptron will look something like this:

![Perceptron built without any frame](assets/built_noframe.jpg)

With a 3D printer, you can print the frames and make it look like this:

![Perceptron built with frame](assets/built.jpg)

If you don't have a 3D printer but still at least want a front plate for the weight knobs, there are some simple things you can do with sheet metal. Either way, it will work the same.

# 1. Obtain the PCBs

There are 2 PCBs - the *Input board* and the *Adder board* - and you can get them from a fabricator such as [JLCPCB](https://jlcpcb.com/) or [PCBWay](https://www.pcbway.com/). If you've never done this before, it may sound intimidating, but I can assure you that it's quite simple. I'll explain how to do it.

The only friction is a bit of cost. The fabricators generally require a minimum order of 5 boards for each PCB design, and since they're in China, there's shipping and tarrif costs as well. The cost of 5 boards is about $15; multiply that by 2, since there are 2 different PCBs; the shipping cost is about $50; and the tariffs are about $15. So the total cost is about $95. On the plus side, for that cost, you'll have 5 of each PCB, and they ship pretty quickly.

I'd love to see more people building these, so if this cost is a real barrier, I'd be happy to get a bunch of these boards made and then send them directly to you. Just let me know. After all, the per-PCB cost is actually quite low, especially when ordered in decent quantities.

Right now, my recommendation is to use JLCPCB - they build and ship quickly, their quality is great, and their Web interface is quite easy to use. PCBWay is also great and easy to use, but sometime recently they stopped accepting payment by PayPal or credit card, so it's a bit difficult to do the actual purchase. Hopefully, they'll fix that soon. I'll explain the generic steps that work for either site, and I'll provide a detailed step-by-step with screenshots for JLCPCB.

The way you do this is by uploading the Gerber files to the fabricator's website. Gerber files are special files that provide all of the information that the fabricator needs to manufacture the PCBs. For each PCB design, all of the Gerber files are packaged together in a single zip archive file. You'll find the two Gerber zip files for the two PCBs in the `PCBs` directory:
- [`PerceptronInputGerbers.zip`](PCBs/PerceptronInputGerbers.zip)
- [`PerceptronAdderGerbers.zip`](PCBs/PerceptronAdderGerbers.zip)

Download them both to your local machine.

Now, go to the fabricator's website and find the place to "Get instant quote" or similar. That should bring you to a page that has a button to "Add Gerber file" or similar. Click that button and upload either one of the Gerber zip files you just downloaded. The website will upload and process the file (which may take a few minutes), and then it will show you a preview of the PCB with the dimensions automatically detected. For the Input PCB, the dimensions should be 164mm x 86mm. For the Adder PCB, the dimensions should be 122mm x 132mm. Now you can "Save to cart." There's no need to change any of the specifications or options - the defaults are fine. Now repeat for the other PCB. With both PCBs in your cart, you can proceed to checkout in the standard way.

[Here](JLCPCB.md) is the step-by-step with screenshots for JLCPCB.

They'll probably take a little over a week to arrive. Rejoice!

![PCBs](assets/pcbs.jpg)

# 2. Obtain all of the other components

[Here](BoM.csv) is the bill of materials (BoM) for all of the components you'll need:

[![Bill of Materials](assets/bom.png)](BoM.csv)

There's also a [PDF version](assets/bom.pdf) of the BoM if you prefer.

For each component, I've tried to find an inexpensive, readily-available option, and I've put links to them in the `Link` and `Alt Link` columns. The one exception is the meter. The only inexpensive source I could find is AliExpress. They're cheap but coming from China. See below for more information about obtaining the meter.

The `Value` column is used to identify each component on the schematic and the PCB layout. It will come into play when we get to building, but for now, you can ignore that column.

The `Qty` column tells you how many of each component you'll need, but realize that the Amazon links go to products that are packs with multiple components. For example, the Amazon LEDs is a pack of 100, so you only need to order one. So for each item you order, make sure you check the number of components in the pack against the quantity needed. The exception is the Digikey links. From Digikey, you can order exactly the number of components you want. In general, I recommend using Digikey, but in the case of the toggle switches, I wasn't able to find an inexpensive option on Digikey.

## Battery holders (to crimp or not to crimp)

There's no provision for an on-off switch on the PCBs (including one seemed like overkill), so to turn the device on and off, you'll need to either have an easy way to connect and disconnect the battery holders to and from the PCB or use battery holders that have an on-off switch built in. I don't much like the battery holders with on-off switches (there's no good way to mount them inside my 3D-printed frames), so I recommend using standard battery holders with a pin header and socket for easy connect and disconnect. To do this, you'll need to be able to do simple crimping. If you've never done it before, don't worry - it's easy and a crimping tool is cheap.

The `Alt Link` for the battery holders is to holders that do have an on-off switch built in, so if you use those, you can just solder the wire leads directly to the PCB like this:

![Battery holders with switches soldered directly to PCB](assets/battery_direct.jpg)

Easy, but I don't much like it - not just because I don't much like the holders with switches, but because it's just awkward to have the holders permanently soldered to the PCB. Better is to connect the battery holders to the PCB with a pin header and socket like this:

![Battery holders connected via pin header and socket](assets/battery_crimp.jpg)

You can also use this method to connect the meter to the other PCB. Again, much better than soldering directly to the PCB.

## Pin headers and sockets

The `Link` for the 2-pin and 4-pin headers and sockets (rows 5-8) in the BoM goes to a full kit of Dupont connectors with plenty of pin headers and sockets with a range of pin counts. You'll just need one of these kits, and you only need the 2-pin size for the meter and the 4-pin size for the battery holders. This one comes with a crimping tool, and the Amazon page also has a short video demonstrating how to use it. It's easy, but if you've never done it before, experiment first with some scrap wire before crimping to the battery holders. Of course, if you already have a crimping tool, feel free to buy connectors without the tool. Also, feel free to use whatever style of pin headers and sockets you prefer. Just make sure that they connect and disconnect easily for the batteries, since that's the on-off switch (unless you use battery holders with built-in on-off switches), and that the pitch (distance between pins) is 2.54mm.

For the 2x10-pin headers, you just need to make sure that the pitch is 2.54mm and that they will accomodate the ribbon cable. For the ribbon cable, I recommend going as short as you can find.

## Meter

For the meter, you need an analog DC current meter that measures current in both directions and with a reasonable range for this particular circuit. I've found that ones that measure from minus 100 microamps to plus 100 microamps (with a full scale voltage around 100 millivolts and therefore a shunt resistance around 1 kohm) are about right for this circuit.

I've tested the one from AliExpress in the BoM, and it works well, so I recommend going with that. It's cheap, and I think it's readily available, albeit coming from China.

Feel free to look around for other alternatives. There are some very nice alternatives from Simpson that you might find on eBay, but they're rather expensive. The one you see in my video is a Simpson model 1329 that I found on eBay. I think it looks great, but it was expensive.

The PCB has a place for a shunt resistor which can help accomodate a wider range of meters. [This video](https://www.youtube.com/watch?v=4U-nxdp-LDw) provides a good explanation of how to use a shunt resistor to accomodate a wider range of meters. If you're using the meter from the BoM or a Simpson like the one I used in the video, then don't put a shunt resistor on the PCB - leave that spot unpopulated.

## Other components

Feel free to use components other than those linked in the BoM. For the toggle switches, just make sure they're DPDT (double-pole double-throw), and that the pin configuration matches. For the potentiometers, just make sure they're 10k ohm and that the pin configuration matches. For the potentiometer knobs, just make sure they fit your potentiometers. For the LEDs, just make sure that the lead spacing is 2.54mm. For the resistors, there are tons of choices but make sure to match the resistance values (68 ohms and 10k ohms), and make sure they're no longer than 6.5mm. For the wire, pretty much anything will work, but I recommended stranded wire at around 22-26 guage.

# 3. Solder the components to the PCBs

Both PCBs are double-sided, so you'll need to solder components to both sides. The silkscreen markings indicate on which side and where each component goes. I recommend doing the rear side of each board first. Here is a photo of the rear side of both boards.

![Rear side of both PCBs](assets/pcbs_rear.jpg)

This side is where the resistors and pin headers go. These components are mounted on the rear side, so of course, you solder on the front side.

The 16 resistors, R1-R16, on the Input board are the 68 ohm resistors, and the 36 resistors, R1-R36, on the Adder board are the 10k ohm resistors. Leave R37, the shunt resistor location, unpopulated, unless you're using a meter that requires a shunt resistor (as desribed above).

When it comes to inserting the 2x10-pin headers, J1 on both boards, if they are notched - as is the case with the ones in the BoM - then you need to make sure that they are inserted in the same orientation on both boards so that the ribbon cable can connect the two boards without having to be twisted. If you insert both connectors with the notch aligned with the marking on the slikscreen, then you'll be fine. ([Here](assets/orient_2x10_header.jpg) is a close-up image.) In general, so long as you can connect the two boards without twisting the ribbon cable, then you're good to go. This is what it should look like:

![Ribbon cable connecting the two boards without twisting](assets/ribbon_cable.jpg)

If you're going to solder the battery holder wires and meter wires directly to the PCBs, then best to do that later, after you've mounted the front-side components. Otherwise, go ahead and solder in the 4-pin header, J2 of the Input board, and the 2-pin header, J2 of the Adder board. The rear side of both boards, now done, should look like this:

![Rear side of both PCBs with rear done](assets/pcbs_rear_rear_done.jpg)

This is now a good time to clean the front side of both boards - the side where you just did the soldering. A scrub with a stiff-bristled brush and isopropyl alcohol will do the trick.

Now on to the front-side components (which, of course, get soldered on the rear side). Here is a photo of the front side of both boards with all of the rear-side components already soldered in place.

![Front side of both PCBs with rear done](assets/pcbs_front_rear_done.jpg)

Starting with the front side of the Input board, this is where the 16 toggle switches, SW1-SW16, and 16 LEDs, D1-D16, go. The toggle switches can go in in either orientation.

The LEDs, however, require more care. You'll notice that the LEDs have a long lead and a short one. ([Here](assets/orient_led.jpg) is a close-up image.) At the very least, make sure that they're all installed with the same orientation - either all with the long lead on the right or all with the long lead on the left. If you're using the LEDs from the BoM, then if you install with the long lead on the right, then you'll get red for plus one (toggle switch up) and green for minus one (toggle switch down). That's how I did it. If you prefer the opposite, then just install with the long lead on the left.

**Important**: If you are going to use the 3D printed frames, don't solder the LEDs until you've read the last section. The LEDs need to be mounted a few millimeters above the board, aligned with the top of the toggle switch housings and the frame's front plate. Fortunately, I've created a 3D printable input-board soldering jig to make this super easy. You're going to want to print out this jig and follow the instructions to use it in order to ensure that you have the LEDs at the right height above the PCB.

Moving on to the front side of the Adder board, this is where the 17 potentiometers, RV1-RV17, go.

Go ahead and clean the rear side of both boards now. Your PCBs are now done. They should look like this (in this case with the LEDs mounted a few millimeters above the board using the 3D printed jig):

![Front side of both completed PCBs](assets/pcbs_front_all_done.jpg)

You don't really need them, but for completeness, here are the schematics for the two PCBs. If you click on the schematic image, you'll get the PDF version.

Input board schematic:

[![Input PCB schematic](assets/schematic_input.png)](assets/schematic_input.pdf)

Adder board schematic:

[![Adder PCB schematic](assets/schematic_adder.png)](assets/schematic_adder.pdf)

# 4. Connect the battery holders and meter and ribbon cable

# 5. (Optional) Build frames