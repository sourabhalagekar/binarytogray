# BINARY TO GRAY CODE CONVERTER USING TRANSMISSION GATES
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
## 2. INSTALLATION OF TOOLS
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
##  REFERENCE CIRCUIT DIAGRAM
![reference circuit diagram](https://github.com/sourabhalagekar/binarytogray/blob/main/bg2.png)
## IMPLEMENTATION
- The basic circuit for constructing this binary to gray code converter is the transmission gate and inverter. 
Each Transmission gate  and inverter is a CMOS  based implementation, and is sized uniformly with (W/L)pFET/(W/L)nFET = (20/1u)/(10/1u).
### Constructing the transmission gate
The transmission gate logic is used to solve the voltage drop problem of the pass transistor logic. This technique uses the complementary properties of NMOS and PMOS transistors. i.e. NMOS devices passes a strong '0' but a weak '1' while PMOS transistors pass a strong '1' but a weak '0'.The pmos and nmos are connected parallel to each other
![reference circuit diagram](https://github.com/sourabhalagekar/binarytogray/blob/main/bg3.PNG)


-There are totally 6 inverters and 3 transmission gates used to construct this binary to gray code converter circuit
After connecting all the transmission gates and inverters according to the reference circuit we obtain our final circuit
Label each and every component and port and check electrical rule checking and generate netlist file using spice and make changes in netlist to add sky130 models. 


 ### IMPLEMENTED CIRCUIT
 ![reference circuit diagram](https://github.com/sourabhalagekar/binarytogray/blob/main/bg4.png)

-The netlist generated initially is as shown below:

* C:\Users\Dell\AppData\Roaming\SPB_16.6\eSim-Workspace\hacakthonbtg\hacakthonbtg.cir

* EESchema Netlist Version 1.1 (Spice format) creation date: 02/10/22 15:54:57

* To exclude a component from the Spice Netlist add [Spice_Netlist_Enabled] user FIELD set to: N
* To reorder the component spice node sequence add [Spice_Node_Sequence] user FIELD and define sequence: 2,1,0

* Sheet Name: /
 
 
M1  /A /B /G0 /vdd mosfet_p	

M10  /G0 /B Net-_M10-Pad3_ GND mosfet_n		

M2  /B /A /G0 /vdd mosfet_p		

M11  /G0 Net-_M10-Pad3_ /B GND mosfet_n	

M3  /vdd /A Net-_M10-Pad3_ /vdd mosfet_p		

M12  Net-_M10-Pad3_ /A GND GND mosfet_n		

M4  /B /C /G1 /vdd mosfet_p		

M13  /G1 /C Net-_M13-Pad3_ GND mosfet_n		

M5  /C /B /G1 /vdd mosfet_p		

M14  /G1 Net-_M13-Pad3_ /C GND mosfet_n		

M6  /vdd /B Net-_M13-Pad3_ /vdd mosfet_p		

M15  Net-_M13-Pad3_ /B GND GND mosfet_n		

M7  /C /D /G2 /vdd mosfet_p		

M16  /G2 /D Net-_M16-Pad3_ GND mosfet_n		

M8  /D /C /G2 /vdd mosfet_p		

M17  /G2 Net-_M16-Pad3_ /D GND mosfet_n		

M9  /vdd /C Net-_M16-Pad3_ /vdd mosfet_p		

M18  Net-_M16-Pad3_ /C GND GND mosfet_n		

U1  /D /B /C /A /G2 /D /G0 /G1 /vdd PORT		

.end


**The netlist after making sky130 models syntax changes is as shown below:**

.lib "sky130_fd_pr/models/sky130.lib.spice" tt

xM1  A B G0 vdd sky130_fd_pr__pfet_01v8 w=1 l=0.5		

xM10  G0 B Net-_M10-Pad3_ GND sky130_fd_pr__nfet_01v8 w=1 l=0.5		

xM2  B A G0 vdd sky130_fd_pr__pfet_01v8 w=1 l=0.5		

xM11  G0 Net-_M10-Pad3_ B GND sky130_fd_pr__nfet_01v8 w=1 l=0.5		

xM3  vdd A Net-_M10-Pad3_ vdd sky130_fd_pr__pfet_01v8 w=1 l=0.5		

xM12  Net-_M10-Pad3_ A GND GND sky130_fd_pr__nfet_01v8 w=1 l=0.5	

xM4  B C G1 vdd sky130_fd_pr__pfet_01v8 w=1 l=0.5		

xM13  G1 C Net-_M13-Pad3_ GND sky130_fd_pr__nfet_01v8 w=1 l=0.5		

xM5  C B G1 vdd sky130_fd_pr__pfet_01v8 w=1 l=0.5		

xM14  G1 Net-_M13-Pad3_ C GND sky130_fd_pr__nfet_01v8 w=1 l=0.5		

xM6  vdd B Net-_M13-Pad3_ vdd sky130_fd_pr__pfet_01v8 w=1 l=0.5		

xM15  Net-_M13-Pad3_ B GND GND sky130_fd_pr__nfet_01v8 w=1 l=0.5		

xM7  C D G2 vdd sky130_fd_pr__pfet_01v8 w=1 l=0.5		

xM16  G2 D Net-_M16-Pad3_ GND sky130_fd_pr__nfet_01v8 w=1 l=0.5		

xM8  D C G2 vdd sky130_fd_pr__pfet_01v8 w=1 l=0.5		

xM17  G2 Net-_M16-Pad3_ D GND sky130_fd_pr__nfet_01v8 w=1 l=0.5

xM9  vdd C Net-_M16-Pad3_ vdd sky130_fd_pr__pfet_01v8 w=1 l=0.5		

xM18  Net-_M16-Pad3_ C GND GND sky130_fd_pr__nfet_01v8 w=1 l=0.5		
		
vdd vdd GND dc 3.5

vd0 A 0 pulse(0 1.8 0s 0s 0s 5us 10us)

vd1 B 0 pulse(0 1.8 0s 0s 0s 10us 15us)

vd2 C 0 pulse(0 1.8 0s 0s 0s 5us 10us)

vd3 D 0 pulse(0 1.8 0s 0s 0s 5us 10us)

.tran 0.1us 50us

.control

run

plot V(A)+35 V(B)+30 V(C)+25 V(D)+20 V(G0)+15 V(G1)+10 V(G2)+5 V(D)

.endc

.end

## RESULTS:

![reference circuit diagram](https://github.com/sourabhalagekar/binarytogray/blob/main/bg5.png)
#### WAVEFORM
![reference circuit diagram](https://github.com/sourabhalagekar/binarytogray/blob/main/bg6.png)

##  REFERENCES:
***
[1] Ravi Kumar Anand “High Performance Binary to Gray Code Converter using Transmission GATE” Int. Journal of Electrical & Electronics Engg.,Vol. 2, Spl. Issue 1 (2015)


[2] G. Sujatha and Dr. Narayanam Balaji ” Design and Implementation of combinational circuits in different low power logic styles” IOSR Journal of VLSI and Signal Processing (IOSR-JVSP) Volume 5, Issue 6, Ver. II (Nov -Dec. 2015)


[3] https://www.udemy.com/course/vsd-intern-10-bit-dac-design-using-esim-and-sky130/


## ACKNOWLEDGEMENT
* [Kunal Ghosh](https://github.com/kunalg123), Co-founder of VLSI System Design (VSD) Corp. Pvt. Ltd 
* [SAFAL COE ,KARNATAKA](https://www.sfalcoe.com/)

## AUTHOR
SOURABH D HALAGEKAR , 7th sem B.E (ECE),  CANARA ENGINEERING COLLEGE 









