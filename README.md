# 16-Bit MIPS-Style CPU in Logisim

**A custom 16-bit processor designed and implemented in Logisim Evo.**

<img width="1280" height="563" alt="image" src="https://github.com/user-attachments/assets/108c144c-fbf2-4cc4-ad96-68ee73d278ff" />


**Author:** Jalil Ayman Afroz (Ayman)  
**Logisim Version:** Logisim Evo 3.6.1.1  
**Platform:** Windows 11 (compatible with macOS/Linux)

---

## Overview

This project implements a **16-bit MIPS-inspired CPU** from scratch using **Logisim Evo**. It supports three instruction formats (**R-type**, **I-type**, and **J-type**) and includes a complete datapath with:

- 8 general-purpose 16-bit registers (`$r0` – `$r7`)
- Arithmetic Logic Unit (ALU)
- Data and instruction memory
- Program Counter (PC)
- Support for branching, function calls (`call`/`rtn`), and memory operations

The design closely follows classic computer architecture principles while being simplified for educational purposes and Logisim implementation.

## Features

- **Three instruction types**: R-type, I-type, J-type
- **16-bit data path**
- **8 registers** (3-bit addressing)
- **Signed 6-bit immediates** (with custom bit placement)
- **Memory operations** (load/store)
- **Control flow**: conditional branches, unconditional jump, function call/return, halt
- Fully functional in Logisim Evo

## Instruction Formats

### R-type (Register)


