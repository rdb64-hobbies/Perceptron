Perceptron Build Guide
===========================

This guide will walk you through building a Perceptron. For more information about the Perceptron and this project, see the [README](README.md). The only required skill is basic soldering of simple through-hole components to printed circuit boards (PCBs). Bonus if you have a 3D printer to make it look nice (as in the image above).

The outline of the build process is as follows:

1. Obtain the PCBs.
2. Obtain all of the other components.
3. Solder the components to the PCBs.
4. Connect the battery holders and meter and ribbon cable.
5. (Optional) build frames.

The last step is optional for those who want to make it look nice. You'll need a 3D printer or some basic skills with sheet metal. Without this step, your Perceptron will look something like this:

![Perceptron built without any frame](assets/built_noframe.jpg)

With a 3D printer, you can print the frames and make it look like this:

![Perceptron built with frame](assets/built.jpg)

If you don't have a 3D printer but still at least want a front plate for the weight knobs, there are some simple things you can do with sheet metal. Either way, it will work the same.

# 1. Obtain the PCBs

There are 2 PCBs - the Input board and the Adder board - and you can get them from a fabricator such as [JLCPCB](https://jlcpcb.com/) or [PCBWay](https://www.pcbway.com/). If you've never done this before, it may sound intimidating, but I can assure you that it's quite simple. I'll explain how to do it.

The only friction is a bit of cost. The fabricators generally require a minimum order of 5 boards for each PCB design, and since they're in China, there's shipping and tarrif costs as well. The cost of 5 boards is about $15; multiply that by 2, since there are 2 different PCBs; the shipping cost is about $50; and the tariffs are about $15. So the total cost is about $95. On the plus side, for that cost, you'll have 5 of each PCB, and they ship pretty quickly.

I'd love to see more people building these, so if this cost is a real barrier, I'd be happy to get a bunch of these boards made and then send them directly to you. Just let me know. After all, the per-PCB cost is actually quite low, especially when ordered in decent quantities.

Right now, my recommendation is to use JLCPCB - they build and ship quickly, their quality is great, and their Web interface is quite easy to use. PCBWay is also great and easy to use, but sometime recently they stopped accepting payment by PayPal or credit card, so it's a bit difficult to do the actual purchase. Hopefully, they'll fix that soon. I'll explain the generic steps that work for either site, and I'll provide a detailed step-by-step with screenshots for JLCPCB.

The way you do this is by uploading the Gerber files to the fabricator's website. Gerber files are special files that provide all of the information that the fabricator needs to manufacture the PCBs. For each PCB design, all of the Gerber files are packaged together in a single zip archive file. You'll find the two Gerber zip files for the two PCBs in the `PCBs` directory:
- [`PerceptronInputGerbers.zip`](PCBs/PerceptronInputGerbers.zip)
- [`PerceptronAdderGerbers.zip`](PCBs/PerceptronAdderGerbers.zip)

Download them both to your local machine.

Now, go to the fabricator's website and find the place to "Get instant quote" or similar. That should bring you to a page that has a button to "Add Gerber file" or similar. Click that button and upload either one of the Gerber zip files you just downloaded. The website will upload and process the file (which may take a few minutes), and then it will show you a preview of the PCB with the dimensions automatically detected. For the Input PCB, the dimensions should be 164mm x 86mm. For the Adder PCB, the dimensions should be 122mm x 132mm. Now you can "Save to cart." There's no need to change any of the specifications or options - the defaults are fine. Now repeat for the other PCB. With both PCBs in your cart, you can proceed to checkout in the standard way.

[Here](JLCPCB.md) is the step-by-step with screenshots for JLCPCB.
