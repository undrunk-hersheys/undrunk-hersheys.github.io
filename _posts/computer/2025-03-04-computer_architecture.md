---
layout: post
title:  "computer_architecture"
date:   2025-03-04 16:01:00 +0900
categories: computer
---

When learning of the computer architecture, just wondered of why learning MIPS instead of ARM or RISC-V architecture.  
Since mips is also one of the risc architecture processors, which is low powered used in embedded computings.  
But most of the current trend is to use the ARM and RISC-V for embedded or industrial stuffs.  
Will the MIPS be doomed forever? Assume only for some of the legacy systems or educational pupose, but its competiveness is been lost.  
But since in the university, using the book for MIPS, and MIPS, ARM, RISC-V are all based on RISC (Reduced Instruction Set Computer), main concepts for CPU structure, pipelining, cach memory, and instruction design are literally the same.  

| Category                     | MIPS                               | ARM                               | RISC-V                           |
|-----------------------------|---------------------------------|---------------------------------|---------------------------------|
| ISA Type                    | RISC                              | RISC                              | RISC                              |
| Instruction Length          | Fixed 32-bit                      | Variable 32/64-bit (Thumb)        | 32/64/128-bit                     |
| Number of Instructions      | Relatively large                  | Adaptive, multiple modes          | Simplest basic ISA                |
| Branch Delay Slot           | Present                           | Not present                       | Not present                       |
| Instruction Format          | Simple three-address format       | Supports multiple modes           | Simple three-address format       |
| Load/Store Model            | Strict RISC principle            | Some CISC-like instructions       | Pure RISC style                   |
| Market Adoption             | Declining                         | Dominates mobile & embedded       | Growing with open-source          |
| Instruction Differences     | Uses "Branch Delay Slot"          | No Branch Delay Slot              | No Branch Delay Slot              |
| Instruction Syntax          | `add $t0, $t1, $t2`               | `ADD R0, R1, R2`                  | `add x1, x2, x3`                  |
| Registers                   | Fixed 32 registers (`$t0, $s0`)   | Variable (16, 32, etc.)           | Fixed 32 registers (`x0-x31`)     |
| ARM Thumb Mode              | Not available                     | Supports 16-bit Thumb mode        | Not available                     |
| System Calls                | `syscall` (`$v0` for function ID) | `svc` (Supervisor Call)           | `ecall` (Environment Call)        |
