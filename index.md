---
layout: page
title: 
permalink: /
---

***ISCA Tutorial***  
*June 19, 2022*  
*New York City, New York, USA*

## Overview

The Instruction-Set Architecture (ISA) has long served as the software/hardware interface for programmable processors.
The ISA simultaneously serves as a specification for the hardware implementation and as an abstraction of the hardware for software development.
Over the years, this interface has enabled independent development of the hardware and software.
This has enabled ISA-compliant hardware upgrades and portability of software applications.
With the advent of multiprocessors, the memory consistency model (MCM) provided the software/hardware interface for processor interactions through shared memory.
As with the ISA, the MCM serves both as the specification for the hardware and its abstraction for software.
We are now in an era where accelerator-rich platforms are widely used to deliver the power-performance requirements of emerging applications.
Unfortunately, there is no widely accepted software/hardware interface for these platforms - this has implications for both hardware and software development.
The accelerator specifications are typically informal, with the possible availability of executable reference models (C/C++/SystemC).
The software development largely depends on APIs providing platform-specific hardware functions calls for utilizing the hardware specialization - similar to how peripheral devices are accessed.
This results in software that is not portable across platforms or optimizable using standard compiler flows.

The recently developed Instruction-Level Abstraction (ILA) provides a software/hardware interface that generalizes the notion of ISAs to accelerators.
The ILA model of an accelerator is a functional model that defines the response of the accelerator to commands at its interface.
These commands serve as “instructions” for the accelerator.
These commands are generally memory-mapped input-output (MMIO) instructions issued by a host processor - thus, there is a one-to-one mapping of these MMIO instructions and ILA instructions of the accelerator.
As with the ISA, the ILA defines the architectural state of the accelerator as the state that is persistent across instructions.
Again, as with the ISA, the ILA is a modular specification that defines how this architectural state is updated by each instruction.
Further, the ILA-MCM model shows how the operational ILA model can be integrated with an axiomatic memory consistency model for a detailed functional specification that includes accelerator-processor interactions through shared memory.

---

## Tentative Schedule

In this tutorial we will introduce the ILA model and its application to the different use cases for accelerator-rich platform highlighted above.

- **1:30 - 1:40 PM:** ***Software/Hardware Interfaces***  
Review the need for new software-hardware interfaces for accelerator-rich platforms
- **1:40 - 2:30 PM:** ***ILA Models***  
Formally define the ILA model including the instructions, architectural state and per-instruction state update functions - this makes the model amenable to formal analysis tools
- **2:30 - 3:00 PM:** ***Break***
- **3:00 - 3:20 PM:** ***Formal Hardware Verification***  
Show how the formal ILA model can be used for formal verification of the hardware implementation
- **3:20 - 3:35 PM:** ***Simulation and Co-simulation***  
Show how the ILA model enables automated generation of executable functional models (C++/SystemC) that can be used in hardware simulation and hardware-software co-simulation
- **3:35 - 3:50 PM:** ***Formal Software-Hardware Co-verification***  
Show how the ILA model enables hardware-software co-verification using software verification techniques
- **3:50 - 4:10 PM:** ***Memory Consistency***
Show how the ILA-MCM model can be used to reason about correctness of code executing across processors and accelerators for a given MCM
- **4:10 - 5:00 PM:** ***Compilation for Accelerator Design Feedback***  
Show how the ILA instructions can be used in a compiler flow for early feedback on accelerator designs – illustrated for deep-learning accelerators using the TVM compiler framework

---

## Resources

- "[Instruction-Level Abstraction (ILA): A Uniform Specification for System-on-Chip (SoC) Verification](https://dl.acm.org/doi/abs/10.1145/3282444)" on the ILA formal model (TODAES 2019 best paper award).
- The ILAng platform [repository](https://github.com/PrincetonUniversity/ILAng) and [user manual](https://bo-yuan-huang.gitbook.io/ilang/).

---

## Organizers

- Sharad Malik (Princeton University)
- Aarti Gupta (Princeton University)
- Zachary Tatlock (University of Washington)
- Bo-Yuan Huang (Intel Corporation)[\*]


[\*]Contents presented do not express the views or opinions of Intel Corp.
