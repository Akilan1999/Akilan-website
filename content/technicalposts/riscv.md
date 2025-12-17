---
title: "Challenging myself to understand RISC-V"
summary: Basics of what is RISC-V
date: 2021-05-30
aliases: ["/riscv"]
tags: ["RISCV","Open Source"]
author: "Akilan Selvacoumar"
draft: false
weight: 2
---

## Why do we need open standards for CPU Architecture ? 

- We want to allow users to see all the parts of the architecture 
without any proprietary constraints. 
- We want to have the rights to modify and distribute without paying any licensing fees and constraints in sharing. 
- With open standards it's easier to build on top of others work and possibly build CPU designs custom made for certain tasks. 

## What is RISC-V ? 
RISC-V is just an open source ISA (Instruction Set Architecture). An ISA is the software interface for the hardware. A single ISA can 
have many hardware implementations. In technical terms as ISA defines set of Instructions and how they behave such as:
- Data types 
- Registers 
- Addressing modes 
- memory models 
- Protection levels 
- How is I/O are done 
- Virtual memory 
- Exceptions 

Another important factor to understand is that RISC-V is a standard
and not an implementation. This means that the entire ISA is defined in a huge latex file which can be found on Github. 

Repo link: https://github.com/riscv/riscv-isa-manual

The RISC-V is a well organized ISA and is divided into various categories and extensions in order to keep it as a modular design.
The RISC-V is maintained the non profit organization called [RISC-V foundation](https://riscv.org/).

### ["RISC-V in contrast was made specifically to be easy to teach while pragmatic enough to actually allow the implementation of high performance microprocessors."](https://medium.com/swlh/risc-v-assembly-for-beginners-387c6cd02c49)

## Few companies working on RISC-V 
- [NVIDIA](https://riscv.org/wp-content/uploads/2017/05/Tue1345pm-NVIDIA-Sijstermans.pdf): using RISC-V in it's GPU
- [SiFive](https://www.sifive.com/): Startup that allows you to create your own RISC-V board or use exsisting models they provide with great toolkits around them. 
- [Western Digital](https://blog.westerndigital.com/risc-v-swerv-core-open-source/): Focusing on building custom
RISC-V cores. 

## Complier support for RISC-V ISA

- [GCC](https://github.com/riscv/riscv-gnu-toolchain)
- [LLVM/Clang](https://github.com/sifive/riscv-llvm) 
- [glibc](https://sourceware.org/git/?p=glibc.git) 
- [Go](https://github.com/riscvarchive/riscv-go) 
- [Rust](https://github.com/riscv-rust/riscv-rust-quickstart) 

## How is the RISC-V ISA organized 
In this section we look into how RISC-V is organised

### RV N (Extension letter)
- RV stands for RISC-V
- N - Number of bits (Ex: 32 bits)
- Extension letter: This is the Extension for the instruction 
sets (I stands for Integer)

### Example Base ISA
RV32I, RV64I, RV128I

### Standard Extensions
- M: Math 
- A: Atomic
- F: Floating Point 
- D: Double Precision Floating Point 
#### - G: General Purpose (Includes, Integer, Math, Atomic, Floating Point and Double Precision Floating Point)

### Linux supports 
#### RV64G
This is called as RISC-V 64 bit General Purpose 

## Lets talk a bit indepth of RV32I
RV32I is a base ISA and the easiest to understand. 
RV32I means it's RISC-V 32 bit Integer ISA. 

``` 
Registers: x0-x31 
(x0 is hardwired to 0)
```
Each register is 32 bits which can be called as 1 word. 

![](https://raw.githubusercontent.com/Artoriuz/RV32I-SC/master/images/schematic.png)
Fig 1.0 [Simplified schematics of RV32I](https://github.com/Artoriuz/RV32I-SC)

Now we will recall the basics and try to understand
how to read an instruction. 
```
add rd,rs1,rs2
```
- add: is the opcode 
- rd: is the destination register 
- rs1: Source register 1 
- rs2: Source register 2 

![](/img/rv32i.png) 
Fig 1.1 [Assembly instructions for RV32I](https://github.com/jameslzhu/riscv-card/blob/master/riscv-card.pdf)

![](/img/registersrv32i.png) 
Fig 1.2 [Registers for RV32I](https://github.com/jameslzhu/riscv-card/blob/master/riscv-card.pdf)

## Interesting research papers 
- [Implementing RISC-V System-on-Chip for Acceleration of Convolution Operation and Activation Function Based on FPGA (Field programmable gate arrays)](https://ieeexplore.ieee.org/document/8564810): FGPA are mostly for application specific integrated circuits. An example would be Intel using FGPA to 
prototype new chips. The objective of the paper was to design 
a RISC-V processor for specific tasks such as Convolution functions and activation functions. The result was that the 
RISC-V processor was faster than CPU + co-processor mode and 
used lesser than the CPU + GPU mode. 

- [Towards deep learning using Tensorflow lite on RISC-V](
  https://edge.seas.harvard.edu/files/edge/files/carrv_workshop_submission_2019_camera_ready.pdf  
): This paper focuses on ISA extensions customized for 
machine learning kernels. The software infrastructure implemented was optimized for neural network execution. 
The following was integrated into Tensorflow lite. The 
result was that instructions was reduced by 8X. 


- [A compiler comparison in the RISC-V ecosystem](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=9191411): Comparing LLVM and GCC performance on RISC-V. LLVM and GCC 
produce same binary size but both have different execution
 times.

## Interesting Open Source projects 
- [RISCBoy](https://github.com/Wren6991/RISCBoy): It is an open-source portable games console, designed from scratch.
RISC-V compatible CPU. Has raster graphics pipelines and display controllers. It consists of other infrastructure such as memory 
controllers and GPIO ports. It also consists of a CAD design of 
the PCB layout. 
- [Potato](https://github.com/skordal/potato): The Potato Processor is a simple RISC-V processor written in VHDL for use in FPGAs. It implements the 32-bit integer subset of the RISC-V Specification version 2.0.
- [Vulcan](https://github.com/vmmc2/Vulcan): RISC-V instruction set simulation built for education using flutter.  






















