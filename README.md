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
<img width="687" height="120" alt="R_type" src="https://github.com/user-attachments/assets/a6d74f01-9d70-4ec3-b51f-45f56fc2aec3" />


### I-type (Immediate)
<img width="659" height="103" alt="image" src="https://github.com/user-attachments/assets/eb182e21-dbbe-4cf0-9a94-11ab83e4d879" />
**Immediate (6-bit signed)** is placed in bits: **3, 2, 1, 15, 14, 0** (from MSB to LSB).

### J-type (Jump)
<img width="646" height="102" alt="image" src="https://github.com/user-attachments/assets/3a9faea4-8f2b-4860-b03c-cd293546043e" />


## Supported Instructions

### R-type
| Instruction     | Syntax                | Opcode (14-11) |
|-----------------|-----------------------|----------------|
| `add`           | `add $rd, $rs, $rt`   | `1110`         |
| `and`           | `and $rd, $rs, $rt`   | `1100`         |
| `or`            | `or $rd, $rs, $rt`    | `1101`         |
| `move`          | `move $rd, $rs`       | `0110`         |

### I-type
| Instruction     | Syntax                  | Opcode (14-11) |
|-----------------|-------------------------|----------------|
| `li`            | `li $rd, imm`           | `0111`         |
| `addi`          | `addi $rd, $rs, imm`    | `0110`         |
| `andi`          | `andi $rd, $rs, imm`    | `0100`         |
| `ori`           | `ori $rd, $rs, imm`     | `0101`         |
| `ble`           | `ble $rs, $rt, offset`  | `0010`         |
| `bne`           | `bne $rs, $rt, offset`  | `0011`         |
| `ld`            | `ld $rd, $rs`           | `0000`         |
| `st`            | `st $rs, $rd`           | `0001`         |

### J-type
| Instruction     | Syntax       | Opcode (14-11) |
|-----------------|--------------|----------------|
| `jump`          | `jump addr`  | `1000`         |
| `call`          | `call addr`  | `1010`         |
| `rtn`           | `rtn`        | `1001`         |
| `halt`          | `halt`       | `1111`         |

## Getting Started

### Prerequisites
- **Logisim Evo 3.6.1.1** (recommended) or newer

### How to Run
1. Clone or download this repository.
2. Open the main `.circ` file in Logisim Evo.
3. Load a program into the **Instruction Memory (ROM)** using the provided machine codes.
4. Start the clock (or use single-step mode) to execute instructions.
5. Observe registers, PC, ALU output, and data memory.

## Test Programs

The repository includes four test programs with verified machine codes (see `documentation/Read_Me.pdf` for full tables):

- **Mem-1**: Loop with addition and conditional branch (`ble`)
- **Mem-2**: Bitwise operations (`andi`, `ori`)
- **Mem-3**: Memory load/store + logic operations
- **Mem-4**: Function call (`call`) and return (`rtn`)

## Project Files

- `main.circ` → Main CPU circuit
- `documentation/Read_Me.pdf` → Detailed project report (instruction formats, machine codes, etc.)
- `test_programs/` → Assembly examples and machine code
- `screenshots/` → Circuit screenshots (add your own)



## Future Improvements

- Pipeline implementation
- More ALU operations (sub, shift, etc.)
- Interrupt support
- Better I/O (keyboard/display)

## Author

**JALIL Ayman Afroz**  
This project was developed as part of a Computer Architecture / Digital Design course.


**Star this repo** if you found it useful!  
Feel free to fork and extend it.

Any questions or suggestions? Open an issue.





