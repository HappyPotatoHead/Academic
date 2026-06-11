---
aliases:
  - Program Execution
tags:
  - Notes
  - ICOA
Date: 2023-09-18
Completion: true
obsidianUIMode: preview
---
# CALL
## C - compiler
The compiler converts each higher level language files into assembly files containing assembly language. 

**Why do people prefer higher level language over assembly language**
1. Increases developer's productivity
	1. Coding in higher level language makes it easier for programmers to debug their coding
2. It allows programmers to think in a more natural way
	1. Higher level language is closer to a human language compared to assembly language
3. Increase program maintainability
**Why do some people still use lower level languages**
1. It allows them to exploit the hardware
2. It is used when the program is speed and size critical

## A - Assembler
The assembler converts these .asm files into object files containing machine codes. 
### The assembler follow these steps
1. It reads and uses assembler directives 
	1. .text 
	2. .data
	3. .global sym
2. Changes pseudo-instructions
3. Assign instruction address
4. Inputs the addresses of the labels, variables, etc into symbol table
5. Creates allocation table for items who need addresses that are unknown
#### Passes
**First pass**
Inserts the addresses of the labels, variables and the names into the symbol table
**Second pass**
Uses the symbol table to produce machine codes

### Header
| Object File header | Text segment | Data segment | Allocation Information | symbol table | Debugging infomation | 
| ------------------ | ------------ | ------------ | ---------------------- | ------------ | -------------------- |

## L - Linker
Links all the .obj files together along with the used libraries into a single executable.
The linker will merge the text/data segments
Search for reference in the symbol table
If not found search in a library instead
Determine the absolute memory addresses
Fill in the absolute address in the machine code
### Dynamic & Statically linked libraries
#### Statically linked libraries
1. The library does not update automatically.
2. When the program runs, the entire library is loaded (including the unused parts)
	1. Uses excess space
#### Dynamically linked libraries
1. It only loads when it is actually need
2. The library updates automatically
3. Slower than statically linked libraries

## L - Loader
It runs the program. That's it
### Steps
1. It reads the executable file header and determines the size of the text and data segments
2. Creates a new address space for the program
3. Copies the instruction and data from the executable into the address space
4. Copies the arguments passed to the program to the stack
5. Initialise the machine's registers
	1. $sp -> top of the global data
	2. $gp -> in the middle of the stack
6. Jump to beginning of the program

# Compiler & Interpreter
## Compiler 
It translate the entire programs before executing it

| Advantage                                                                               | Disadvantage          |
| --------------------------------------------------------------------------------------- | --------------------- |
| It is faster                                                                            | It is harder to debug |
| It can optimise code                                                                    |                       |
| Can detect syntax errors before running program                                         |                       |
| Can determine syntax and semantic errors since it has more information than interpreter |                       |

## Interpreter
It translate and executes codes line by line

| Advantage            | Disadvantage                                                     |
| -------------------- | ---------------------------------------------------------------- |
| Easier to debug      | There is no optimisation                                         |
| Instruction set independence | It is slower                                                     |
| Better error message                     | The interpreter has to remain installed while program is running |

# Chapter 6 - Processor, Memory System, and Instruction Execution
[[Chapter 6 - Processor, Memory System and Instruction Execution]]
