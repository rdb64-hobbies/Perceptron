# Perceptron

This repository contains the build guide, PCB designs, manufacturing files (Gerbers), circuit schematics, and bill of materials (BoM), everything you need to build your own Perceptron, just like the one described in this [video tutorial](https://www.youtube.com/watch?v=l-9ALe3U-Fg) by Welch Labs and in this other video tutorial (add link here) by me.

![Perceptron](assets/built.jpg)

This little device is fun to build, and it provides a wonderful hands-on illustration of how neural networks are trained and how they work. It was the Welch Labs video that inspired me to do this, but dreading the prospect of all that point-to-point wire soldering (as in the Welch Labs version), I decided to make a PCB version. With the PCBs, it's really easy to build, and you can use it to teach someone about neural networks. So I hope you'll go ahead and build one.

Go right to the [build guide](BUILDING.md) and get started.

If you already know how to do all of this stuff and just want the Gerber files, circuit schematics, and BoM, then read the [PCBs](#PCBs) section below.

## PCBs

The PCBs were designed using KiCad (https://www.kicad.org/), and you'll find the source files in the `PCBs` directory. There are two PCBs in two KiCad project directories:

- **PerceptronInput** - Input board with toggle switches and bi-color LEDs
- **PerceptronAdder** - Adder board with potentiometers for signal processing

If you just want the Gerber files to order from a PCB manufacturer, you can find them also in the `PCBs` directory. Each one is in its own zip archive file.
