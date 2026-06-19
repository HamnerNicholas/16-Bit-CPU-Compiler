# Custom 8-Bit CPU, Assembler, and Compiler

## Overview

This project is a complete software and hardware stack built from scratch, consisting of:

* A custom 16-bit CPU designed in Logisim
* A custom assembler
* A custom C-inspired programming language compiler
* A custom instruction set architecture (ISA)

The project was developed as a way to explore computer architecture, instruction set design, compiler construction, assembly language programming, and hardware/software integration.

The compiler translates a high-level language into assembly, which is then assembled into machine code and executed on the custom CPU implemented in Logisim.

---

## Features

### Language Features

* Integer variables
* Integer arrays
* Arithmetic expressions
* Operator precedence
* Function definitions
* Function parameters
* Function return values
* Return expressions
* If statements
* While loops
* For loops
* Assembly passthrough
* Integer output
* String output

### Example Language

```c
let result = 0

func add a b = {
    return a + b
}

call add(50,23)

result = RETVAL

print result

halt
```

Output:

```text
73
```

---

## CPU Architecture

The processor is an accumulator-based 8-bit architecture featuring:

* 8 General Purpose Registers
* Program Counter
* Accumulator Register
* Global Memory
* Subroutine Register File
* Hardware Multiply and Divide Support
* Relative Branching
* Function Call and Return Instructions
* TTY Output Device

### Instruction Format

Each instruction is 16 bits:

```text
[ 8-bit Immediate ][ 2-bit Subop ][ 3-bit Register ][ 3-bit Opcode ]
```

---

## Instruction Set

### Arithmetic Immediate

```asm
addi
subi
multi
divi
```

### Arithmetic Register

```asm
add
sub
mult
div
```

### Data Movement

```asm
copy
load
store
```

### Branching

```asm
beq
bne
blt
jump
```

### Subroutines

```asm
jsr
rsr
ssrf
rsrf
```

### I/O

```asm
tty
ttya
halt
```

---

## Function Calling Convention

The compiler uses the Subroutine Register File (SRF) for parameter passing and return values.

```text
SRF0 = Return Value
SRF1 = Parameter 1
SRF2 = Parameter 2
SRF3 = Parameter 3
```

Example:

```c
func multiply a b = {
    return a * b
}

call multiply(5,10)

print RETVAL
```

Output:

```text
50
```

---

## Arrays

Arrays are stored in contiguous memory locations.

Example:

```c
let nums[] = 5,10,15,20

print nums[2]
```

Output:

```text
15
```

---

## Control Flow

### If Statements

```c
if x < y
    print x
endif
```

### While Loops

```c
while x < 10
    x = x + 1
ewhile
```

### For Loops

```c
for i = 0, i < 10, i++
    print i
efor
```

---

## Assembly Passthrough

Raw assembly can be embedded directly into source files.

```c
asm = {
    addi r0 42
    ttya
}
```

This allows access to low-level hardware features that may not yet have a high-level language equivalent.

---

## Compiler Pipeline

```text
Source Program
      ↓
Compiler
      ↓
Assembly Code
      ↓
Assembler
      ↓
Machine Code
      ↓
Custom CPU
```

---


## Example Program

```c
let result = 0

func square x = {
    return x * x
}

call square(11)

result = RETVAL

print result

halt
```

Output:

```text
121
```

---

## Future Improvements

Planned features include:

* Else / Else-If Support
* Dynamic Array Indexing
* Structs
* Local Variables
* Recursive Functions
* Stack-Based Function Calls
* Constant Folding Optimizations
* Dead Code Elimination
* Improved Register Allocation

---

## Motivation

This project was built to gain hands-on experience with:

* Computer Architecture
* Instruction Set Design
* Digital Logic Design
* Compiler Construction
* Assembly Language Programming
* Hardware / Software Co-Design

By implementing every layer of the stack—from hardware to compiler—the project provides a complete view of how software executes on a processor.

---

## Author

Nicholas Hamner

Computer Engineering Student
California State University, Sacramento
