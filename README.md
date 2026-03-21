# Perceptron

This repository contains the build guide, PCB designs, circuit schematics, PCB manufacturing files (Gerbers), bill of materials (BoM), and 3D printable frame designs, everything you need to build your own Perceptron, just like the one described in my [video tutorial](https://www.youtube.com/watch?v=PSqP73T0g_M). It was inspired by this [video tutorial](https://www.youtube.com/watch?v=l-9ALe3U-Fg) by Welch Labs. I hope you'll check out both videos.

![Perceptron](assets/working.jpg)

This little device is fun to build, and it provides a wonderful hands-on illustration of how neural networks are trained and how they work. It was the Welch Labs video that inspired me to do this, but dreading the prospect of all that point-to-point wire soldering (as in the Welch Labs version), I decided to make a PCB version. With the PCBs, it's really easy to build, and you can use it to teach someone about neural networks. So I hope you'll go ahead and build one.

Go right to the [build guide](BUILDING.md) and get started.

If you want to skip this build guide and just jump right in with the schematics, the PCB Gerbers, the BoM, and the 3D-print files, then here they are:

- Schematics:
  - [Input board](assets/schematic_input.pdf)
  - [Adder board](assets/schematic_adder.pdf)
- PCB Gerbers:
  - [Input board](PCBs/PerceptronInputGerbers.zip)
  - [Adder board](PCBs/PerceptronAdderGerbers.zip)
- BoM: [csv file](BoM.csv), [pdf file](assets/bom.pdf)
- 3D-print files: [Frames directory](Frames/)

## PCBs

The PCBs were designed using KiCad (https://www.kicad.org/), and you'll find the source files in the `PCBs` directory. There are two PCBs in two KiCad project directories:

- **PerceptronInput** - Input board with toggle switches and bi-color LEDs
- **PerceptronAdder** - Adder board with potentiometers for signal processing

If you just want the Gerber files to order from a PCB manufacturer, you can find them also in the `PCBs` directory. Each one is in its own zip archive file.

## 3D printable frames

The frames were designed using Fusion 360 (https://www.autodesk.com/products/fusion-360/), and you'll find the source files in the `Frames` directory. The complete Fusion 360 archive file there along with all of the 3D printable 3mf files. The 3mf files come directly from Fusion 360, so they contain only model information, no printer or slicer settings.
