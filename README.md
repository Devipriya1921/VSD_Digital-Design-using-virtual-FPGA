# Digital Design on Virtual FPGA -- VSDOpen21

![vsdopentutorial](https://user-images.githubusercontent.com/80625515/137896513-0cc9dace-0454-43a7-be28-a6ce883cf631.png)


## Contents

- [About the tutorial](#about-the-tutorial)
- [Introduction](#introduction)
- [What is Makerchip?](#what-is-makerchip?)
- [FPGA Boards](#fpga-boards)
- [FPGA Peripherals](#fpga-peripherals)
- [Labs Starting-Point Code](#Labs-Starting-Point-Code)
- [4-Way Traffic Light Controller Design](#4-way-traffic-light-controller-design)
- [References](#references)
- [Author](#author)
- [Acknowledgement](#acknowledgement)


## About the tutorial 

This course had an in-depth hands-on demo session on the Virtual FPGA Lab using the open-source Makerchip IDE Web platform. 
The course had the following contents : 

![tut-1](https://user-images.githubusercontent.com/83152452/138092623-2bbfd083-44a0-45de-8fa2-c7a91c7ddb66.png)

Later on learnt basics of Verilog.
Also we had designed a 4-way traffic light controller using the concept of Finite State Machines in Verilog. 
Then visualized the output with LEDs and seven-segment displays in the Makerchip Virtual FPGA platform. 
Every part of this course had a theory followed by a lab.

For reference, you may want to look into the following repository : [Link](https://github.com/BalaDhinesh/Virtual-FPGA-Lab)


## Introduction

![virtual-fpga](https://user-images.githubusercontent.com/83152452/138095497-fa1a7cfd-2240-479d-86fe-cd493b258625.png)

Field-Programmable Gate Array(FPGA) is a hardware circuit that a user can program to carry out logical operations. FPGAs are beneficial for prototyping application specific 
integrated circuits (ASICs) or processors. The advantage of FPGA being energy-efficient, flexible to reprogram, support parallelism, decreased latency made them widely used 
in many applications. But the flexibility of FPGAs comes at the price of the difficulty of reprogramming the circuit. FPGA’s are a bit costly and difficult to learn for 
beginners. Also, students don’t have access to physical FPGA Lab classes in their curriculum amidst this pandemic situation. 
So there is a massive demand in having an alternative option of having an online simulator for FPGA curriculum development. 

This project " Virtual FPGA Lab ", aims to solve the problem by taking advantage of the ' VIZ Visualization ' feature in the Makerchip platform and provide visualizations 
of basic peripherals of an FPGA, thereby mimicking the physical lab experience.

For more details you may refer : [Link](https://medium.com/@m.baladhinesh/fpgas-in-your-browser-bb92be1c1fa3)


## What is Makerchip?

![makerchip-1](https://user-images.githubusercontent.com/83152452/138096706-c0928bea-2987-4d3a-8e90-467df12d4cee.png)

[Makerchip](http://makerchip.com/) is a free web-based IDE as well as available as [makerchip-app](https://pypi.org/project/makerchip-app/), a virtual desktop application 
for developing high-quality integrated circuits. You can code, compile, simulate, and debug Verilog designs, all from your browser. Your code, block diagrams, 
and waveforms are tightly integrated. Makerchip supports the emerging [Transaction-Level Verilog](http://tl-x.org/) standard. Transaction-Level Verilog, or TL-Verilog, 
represents a huge step forward, by eliminating the need for the legacy language features of Verilog and by introducing simpler syntax. At the same time, TL-Verilog adds 
powerful constructs for pipelines and transactions. 
More details about TL-Verilog: https://www.redwoodeda.com/tl-verilog


## FPGA Boards 


1. Zedboard Zynq-7000 ARM/FPGA SoC Development Board ([Product Link](https://www.avnet.com/wps/portal/us/products/avnet-boards/avnet-board-families/zedboard/))
2. EDGE Artix 7 FPGA Development Board ([Product Link](https://allaboutfpga.com/product/edge-artix-7-fpga-development-board/))
3. Basys 3 Artix-7 FPGA Trainer Board ([Product Link](https://store.digilentinc.com/basys-3-artix-7-fpga-beginner-board-recommended-for-introductory-users/)) 
4. Icebreaker FPGA ([Product Link](https://1bitsquared.com/products/icebreaker))
5. Nexys A7 ([Product Link](https://store.digilentinc.com/nexys-a7-fpga-trainer-board-recommended-for-ece-curriculum/))

Currently we demonstrate using only these boards and we plan to add more boards in the future.


## FPGA Peripherals

#### Board select :

```
m4_define(M4_BOARD, 1)      // This should always be declared for below macros to work

// M4_BOARD numbering
// 1 - Zedboard
// 2 - Artix-7
// 3 - Basys3
// 4 - Icebreaker
// 5 - Nexys
```

#### Board Initailisation :

```
m4+fpga_init()
```

#### LED Module :

```
m4+fpga_led(*led)

// Arguments:
// *led - led signal
```
#### Seven segment display :

```
m4+fpga_sseg(*digit, *sseg, *dp)

// Arguments:
// *digit - common anode signal
// *sseg - seven segments
// *dp - decimal point
```


## Labs Starting-Point Code

### [Template code](https://makerchip.com/sandbox/0zpfRhJYm/0wjhRzo)

![Makerchip-Template code - waveform-1](https://user-images.githubusercontent.com/83152452/138099947-428bb62c-f594-4ba9-9905-d8f6c3d1a924.png)


### [LED starter](https://makerchip.com/sandbox/0v2fWhWqR/0KOhrvN)

![makerchip-LED Starter](https://user-images.githubusercontent.com/83152452/138099961-2249f5a9-3cfd-48e7-96f2-5d703b9eb6bd.png)

https://user-images.githubusercontent.com/83152452/138102760-50f405a2-de58-4eb0-9fe5-349f9422a05e.mp4


### [Seven segment display starter](https://makerchip.com/sandbox/0v2fWhWqR/0Elh6Jx)

![makerchip-7segment-1](https://user-images.githubusercontent.com/83152452/138099971-2d6c7ad5-19e5-4b2a-87fa-25d4c807c8d3.png)


### [Traffic light controller starter](https://makerchip.com/sandbox/0v2fWhWqR/0JZhQm2)

![makerchip-traffic](https://user-images.githubusercontent.com/83152452/138100399-e4a73391-ba59-4ccb-b69c-4d21b250be5a.png)

## 4-Way Traffic Light Controller Design

#### Contents covered :
  
- Introduction to Finite State Machines theory
- Verilog FSM implementation of traffic light controller design
- Integrate with LED and seven-segment

#### Problem Statement

![trafficlight-1](https://user-images.githubusercontent.com/83152452/138100881-8909c2eb-2e19-4442-9d50-15916bee850a.png)


## References

- https://github.com/BalaDhinesh/Digital-Design-on-FPGA--VSDOpen21.git


## Author

- A Devipriya, Bachelor of Engineering (ECE), Cambridge Institute of Technology, Bangalore, adevipriya1900@gmail.com


## Acknowledgement

- Bala Dhinesh, Contributing as a participant in Google Summer of Code 2021, under FOSSi Foundation
- Kunal Ghosh, Co-founder, VSD Corp. Pvt. Ltd. - kunalpghosh@gmail.com
