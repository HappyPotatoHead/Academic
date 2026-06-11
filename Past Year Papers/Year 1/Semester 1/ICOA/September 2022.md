---
aliases:
  - September 2022
tags:
  - PYQ
  - ICOA
Creation Date: 2024-05-22T13:28:00
Completion: true
obsidianUIMode: preview
---
## Question 3
### Question a
#### (i)
| Single-cycle                                                  | Pipeline                                                                         |
| ------------------------------------------------------------- | -------------------------------------------------------------------------------- |
| One instruction must be completed before starting another     | The succeeding instruction begins before the current instruction is completed    |
| The resources are not shared                                  | The resources are shared                                                         |
| The clock cycle is set to accommodate the slowest instruction | The clock cycle is set to accommodate the slowest stage in the instruction cycle | 
#### (ii)
Throughput -> amount of tasks that can be completed in a given amount of time
Latency -> the time taken for a task to be completed.
![[Timing diagram]]
The single-cycle architecture does one instruction within one clock cycle at a time. The pipeline architecture begins the next instructions even before the current one has been completed. This means that the throughput of pipeline is significantly better compared to single cycle. However, the latency of each instruction remains the same in pipeline architecture and single cycle. 
### Question b
#### (i)
1. It can be updated automatically
2. Only calls the library when it is needed so it saves a lot of space
#### (ii)
|             | Advantages                                                                                                                                                                        | Disadvantages    |
| ----------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------- |
| Compiler    | It can optimise code. It runs faster. Can detect syntax error before running. Can do better diagnosis on syntax and semantic error since it has more information than interpreter | Harder to debug. |
| Interpreter | It is easier to debug. Produce better error message since it is closer to human language                                                                                          | No optimisation. Slower to run.                  |

# Section B
## Question 4
### Question a
#### (i)
The wide diversity of hardware interfaces and communication protocols used by different devices.
#### (ii)
Memory-mapped I/O
The I/O addresses are embedded in the memory addresses of the computer. No special instructions are needed to access the I/O addresses. There is no special consideration needed to the processor. It takes up space in the memory address space for I/O mapping.

Isolated I/O
The I/O addresses are separate from the main memory address space. Special instructions are needed to access the I/O device addresses. The user is able to completely utilise the main memory addresses completely. It can be slower.
### Question b
1. Power distribution
	1. The USB devices can be bus powered
2. Control peripherals
	1. Data can flow in both ways
3. Power conservation
	1. It enters a state of suspense when inactive
4. Error checking and recovery
5. Expandable through hub
	1. When a laptop does not have enough USB port, a USB hub can be used
### Question c
#### (i)
Exception
1. Division by 0
2. Arithmetic overflow
Interrupt
1. Syscall in MIPS
#### (ii) 
Exception handling
1. Disable further interrupts
2. Record the cause of interrupts 
3. Transfer control to exception handler. 
	1. The exception handler will record:
		- Program counter
		- The operating mode (user or administration)
		- The state of interrupt (enabled or disabled)
4. Record the return address
**IN MIPS** 
The CAUSE and EPC are stored in \$k0, \$k1 registers. These registers are not a part of the MIPS register files but a part of the coprocessor0. The processor returns to the EPC address stored in \$k1.
## Question 5
### Question a
#### (i)
![[Memory hierarchy|1000]]
*Comparison is in the diagram*
#### (ii)
**Temporal localities**
1. Locality in time
2. When data is recently accessed, it is more likely to be accessed again
3. **How to exploit:** Keep recently accessed data in a higher level of hierarchy
**Spatial localities**
1. Locality in space
2. When data is recently accessed, the nearby data is most likely to be used
3. **How to exploit:** When access a data, bring the nearby data to the higher level of hierarchy
### Question b
#### (i)
*That is a single cycle datapath*
lw \$rt, imm(\$rs)
**Stage 1**
Stage one is instruction fetch. The processor fetches the instructions based on the program counter. When the current instruction is done, 4 bytes are added to the program counter to fetch the next instruction. 
**Stage 2**
Stage 2 is instruction decode. The register file is a group of registers. The processor decodes the instruction in stage 2 to determine the type of instruction format, operands used and the instructions to produce the control signal that will determine the operation that will be carried out. 
**Stage 3**
Stage 3 is instruction execution. The immediate address is signed extended to fill the 16 bits. The secondary register (\$rt) is added to the immediate to determine the address in the memory. 
**Stage 4**
Stage 4 is memory access. The data memory can be read from and written into. Because the instruction is lw, the write enable is turned off. The data memory will read the data from the result of addition between \$rt and immediate. 
**Stage 5**
Stage 5 is write back. The value from the memory is passed back to the register file. The write enabled is turned on and the value is written into \$rt. \$rt now holds the value from the address. 

#### (ii)
Instruction format and registers used