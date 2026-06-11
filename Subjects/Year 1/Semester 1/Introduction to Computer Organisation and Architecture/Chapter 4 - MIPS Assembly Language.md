---
aliases:
  - Assembly Language
tags:
  - Notes
  - ICOA
Date: 2023-09-18
Completion: true
obsidianUIMode: preview
---
# MIPS assembly language
## Four design principles of computer architecture
1. Simplicity favours regularity
	1. MIPS have 3 instruction formats only
		1. R format
		2. I format 
		3. J format
	2. All instructions in R format uses 3 operands
	3. All opcodes are 6 bits
2. Make common case fast
	1. MIPS instructions are simple instructions
	2. The complex instructions are done with multiple simple instructions
	3. Create only regularly used instructions as much as possible
3. Smaller is faster
	1. MIPS only has 32 registers. 
	2. Smaller number of registers allow it to be easier and quicker to access
	3. Larger amount of registers will make the architecture slow as it has to go through more clock cycle to get to the registers
4. Good design demands good compromise
	1. R formats have 3 operands but I format uses 2 operands and an immediate

## CISC vs RISC
CISC is Complex Instruction Set Computer
RISC is Reduced Instruction Set Computer

| CISC                                            | RISC                                            |
| ----------------------------------------------- | ----------------------------------------------- |
| More complex instructions                       | Simpler instructions                            |
| More power consumption                          | Lesser power consumption                        |
| Longer execution time                           | Shorter execution time                          |
| Intel x86                                       | ARM                                             |
| Required less instructions to perform an action | Requires more instructions to perform an action |
| Lesser number of registers                      | More registers                                  | 
## Instructions
| Category             | Instructions |
| -------------------- | ------------ |
| Arithmetic           | add, sub     |
| Logic                | And, Or, Not |
| Conditional branch   | bne, beq     |
| Unconditional branch | j, jal, jar  | 
### load word, store word
**Load word** - lw rt, imm(rs)
Reads from memory and stores value into the register
lw \$s0, 0(\$0)

**Store word** - lw rt, imm(rs)
Stores value from register into memory
sw \$s0, 0(\$0)

- [!] The address must be divisible by 4. This is designed for simplicity
## Big Endian & Little endian
Big endian -> starts with index 0 to index 3
Little endian -> starts with index 3 to index 0
**Load byte** - lb rt, imm(rs)
**Store byte** - lb rt, imm(rs)
**Example**
\$s0 - 0x23456789
**little endian**
lb $s1, 1(\$0) --> 67
**big endian**
lb $s1, 1(\$0) --> 45

## Translation of Instructions into machine code
Find out the hexadecimal/decimal numbers representing the instructions, and registers
If the opcode is 0, the instruction is in R-format
Convert those into binary numbers
Separate the binary numbers into groups of 4. 
Convert each group into hexadecimal numbers

# Coding
## Logical instructions
It still functions the same as ordinary logic gate
## Shift instructions
This can be used to replace multiplication.
There are sll, sra, srl
In both sll and srl, 0 is used to replace the "missing" bits
In sra, 1 is used to replace the "missing" bits

**Format** - sll,srl,sra $s0, $s0, imm
## Multiplication and Division
Multiplication of 32 bits with 32 bits will produce 64 bits
Division of 32 bits with 32 bits will produce 32 bits of quotient and 32 bits of remainder
In mult -> the 32 lsb is stored in lo and the 32 msb is stored in hi
in div -> the 32 bits quotient is stored in lo and the 32 bits remainder is stored in hi
**Formula** - mult \$s0, \$t0 & div \$s0, \$t0
**Formula** - mfhi \$0s0 / mflo \$s0

## Branching 
**bne** - branch not equal
**beq** - branch equal
When the higher level language uses "\==", use bne
When the higher level language uses "!=", use beq
**Formula** - bne/beq \$s0, \&s1, label
In bne, if the two variables are not equal, it will jump to the label
In beq, if the two variables are equal, it will jump to the label.

## Conditional operation
**slt** - set less than
**slti** - set less than immediate

slt \$s0, \$t1, \$t0
If t1 is lesser than t0, s0 will have value of 1. If not, it will have value of 0.

## Loops
**Will put here one day**
## Array
**Summary of how it should work**
1. Set the base address using lui and ori
2. Take out the value from the memory using the base address
3. Process the values
4. Put it back into the memory
5. Increment the base address by 4
## Function Calls
Use jal when calling functions
Use jr $ra when function operations are done
### Local variables
You must first set the stack pointer according to the number of arguments needed.-> at the top of the dynamic data segment
addi \$sp, \$sp, -12 -> moves down 3 times
Put the values into the stack pointers
Proceed with the instructions in the function
Restore the values from the stack pointers into the registers
Restore the stack pointer
Use \$a0 to \$a3 for arguments

# Addressing modes
## Register Addressing mode
Used by R-formats -> arithmetic
![[Base addressing]]
## Immediate Addressing mode
Used by I-formats 
![[Immediate addressing]]
## PC - relative Addressing mode
Used by bne, beq instrcutions
![[Pc-relative addressing|1000]]
## Pseudo-directive Addressing mode
Used by j, jal, jr
![[Pseudodirective displacement|1000]]
## Base (displacement) Addressing mode
For lw, sw, lb, sb
![[Base (displacement) displacement|500]]
# Chapter 5 - Program Execution
[[Chapter 5 - Program Execution]]


