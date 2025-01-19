---
layout: post
title:  "Embedded_HW"
date:   2025-01-19 16:28:00 +0900
categories: embedded
---

First of all, this is the post for the start of the project which contains implementation of the RTOS. And since I was really willing to know of what kinds of board should I choose for the right occation, few researches for the types of boards. 

#### 8bits
ATmega(8bit AVR)  
PIC
:8 bits are used for simple embedded.  
#### 16bits
TI MSP430 Series  
MSP430G2553  
MSP430FR6989  
:used for low power device, wearabel etc.  
Nordic NRF Series  
NRF51/52(ARM Cortex-M0)  
NRF53(ARM Cortex-M33)  
:Bluetooth low energy  

#### 32bits
STM32(ARM Cortex-M)  
ESP32  
NXP  
i.MX  
:32 bits are used for complicated embedded or IoT environment.  
BeagleBone Black(ARM Cortex-A8)
:For the robot control  

#### 64bits
RaspberryPi  
Jetson Nano  
:64 bits are used for AI or Imaging processing works.
 

#### ARM Cortex  
Most used processor. About 90% of the mobile device is designed for ARM core. Cortex-M is combined in STM32, Nordic, NXP..   
About ARM Cortex-M & ARM Cortex-A  

Other Architectures  
x86(intel, AMD): this is for the higher processing computers.  
RISC-V: open source architecture not used as much as ARM.  
MIPS: Used in embedded systems before ARM.  


M(Microcontroller)  
Embedded Systems: Ideal for real-time control, sensor data processing, and single-application execution.  
Low Power Design: Used in battery-operated or energy-sensitive systems.  
RTOS Friendly: Easily integrates with RTOS (Real-Time Operating System) for real-time applications.  
  
Cortex-M0/M0+: Ultra-low power, suitable for basic tasks.  
Cortex-M3: Used for general embedded applications.  
Cortex-M4: Supports DSP (Digital Signal Processing) and FPU.  
Cortex-M7: High-performance real-time control.  
    
A (Application)
OS Support: Capable of running full-stack operating systems like Linux, Android, and Windows.  
High Performance Design: Suitable for multitasking and complex data processing tasks.  
Power Consumption: Higher power consumption compared to Cortex-M, typically used with AC power or large battery-based systems.  
  
Cortex-A5/A7: For low-power mobile devices.  
Cortex-A9: For mid-performance devices.  
Cortex-A53/A55: Balances efficiency and performance.  
Cortex-A72/A75: High-performance computing and multimedia applications.  






