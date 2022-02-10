# binarytogray
This project deals with conversion of Binary code to gray code
## Table of Contents
- [Introduction](#introduction)
- [Installation of tools](#installation_of_tools)
- [Reference_Circuit](#reference_circuit)
- [Implementation](#implementation)
- [Results](#results)
- [References](#references)
- [Acknowledgements](#acknowledgements)
- [Author](#author)
## Introduction
- Low power and area efficient technologies are the prime concern for VLSI system designers. Together with that, the high speed binary to Gray code converter that use low power consumption have indisputably become one of the most crucial components of a processor because they are mostly used in arithmetic logic unit. Transmission gates require lower switching energy and it reduces the count of transistors used to make different logic gates. Transmission gate use less area and less transistors compare with conventional design logic.In this project I have designed and simulated the binary to Gray code converter using transmission gates. the design and Implementation will be done using eSim and ngspice software
- .BINARY TO GRAY CODE CONVERTER--
 This code converter combinational circuit is designed to convert binary to Gray code. The input code of code converter is binary and output code of code converter is Gray code.
![reference circuit diagram](https://www.zzoomit.com/wp-content/uploads/2018/08/Screenshot-304.png)
### 2. INSTALLATION OF TOOLS
***
#### esim:
esim is an open-source EDA tool used for circuit design and simulation. Using esim we can draw circuit using Kicad, generate netlist and simulate using Ngspice.
For more information: <https://esim.fossee.in/home>
#### Ngspice:
ngspice is the open-source spice simulator for electric and electronic circuits. We can design circuits using JFET, MOSFET and passive elements like resistors, capacitors, etc.
For more information: <http://ngspice.sourceforge.net>
#### Sky130nm PDK:
The SkyWater Open Source PDK is a collaboration between Google and SkyWater Technology Foundry to provide a fully open source Process Design Kit and related resources, which can be used to create manufacturable designs at SkyWater’s facility. 

Follow these steps for Sky130 download and implementaion:
1. Download sky130 from this link mentioned above and unzip it.
1. Save the .cir.out file in the sky\_fd\_pr folder as .cir file.
1. Open with notepad and add the path .lib "models/sky130.lib.spice" tt at the top.

6. Now Run the circuit with ngspice.
To Run the ckt using ngspice:
1. Right click on .cir file.
1. Click on Open With.
1. Browse for the ngspice.
1. If ngspice not present scroll down click on More Apps.
1. Go to the FOSSEE folder search for Ngspice and Run it.
