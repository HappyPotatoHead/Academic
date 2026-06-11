---
aliases:
  - September 2021
tags:
  - PYQ
  - ICOA
Creation Date: 2023-10-04T15:22:00
Completion: true
obsidianUIMode: preview
---
# Section A
## Question 3
### Question a
#### (i)
2^4 = 16. The new machine have 16 registers
#### (ii)
Smaller number of registers. The instruction size would be smaller since the number of registers are reduced.
#### (iii)
Have variable-length instructions. Instructions can have varying lengths according to the operands they use
### Question b
No. Each instruction in single cycle is completed in one complete clock cycle but the instructions in multicycle is broken down into multiple stages. The clock rate time in single cycle is set to accommodate the slowest instruction. e.g. lw whereas each stage in multicycle may take one or more cycle to complete. This means that the instructions have to sit through the entire clock cycle even after the instruction has been completed but multicycle prevents idling. The single cycle has poor resource utilisation. The resources cannot be shared and are allocated for all operations even if the are not in use whereas the resources in multicycle can be shared and are only allocated when needed by the instructions. 
### Question c

| Compiler                                                                                        | Interpreter                                            |
| ----------------------------------------------------------------------------------------------- | ------------------------------------------------------ |
| Code runs faster                                                                                | Easier to debug                                        |
| Better diagnosis of syntax and semantic error since it has more information than an interpreter | Closer to high-level, can provide better error message |
| Can detect syntax error before running                                                          | Provide instruction set independence                   |
| Can optimise code                                                                               | Faster development time                                                        |
**Similarities**
Both are used to translate higher level languages into machine codes. Both can detect syntax error
## Question 4
### Question a
#### (i)
CPU does not do data transfer. 
Faster data transfer rate
#### (ii)
Bus arbitration is done. The DMA controller sends a hold request to the CPU to request the CPU to release the memory bus. The CPU will then send hold acknowledge to DMA controller signifying acknowledgement on the hold request and release the memory bus. 
### Question b
1. The MIPS processor disables further interrupts
2. Records the cause of the interrupt into cause register 
	- cause and EPC register is not a part of the MIPS register file
3. Transfer control over to exception handler. Exception handler will
	1. Save the PC (program counter)
	2. Save the current operating mode (user or admin)
	3. Save the status of interrupt (enabled or disabled)
4. Stores return address into EPC
5. Returns to the return address in EPC after the handling the exception
### Question c
SPIM uses memory-mapped device registers to do its input and output. Receiver data and receiver control are used for input whereas transmitter data and transmitter control is used for output. 
Receiver control
1. First bit is Ready bit.
	1. 1 if it is ready
	2. 0 if it is not ready
2. Second bit is Interrupt enabled bit
	1. 1 -> interrupt when data is available
	2. 0 0> do not interrupt when data is available
3. The rest of the bits are not used
Receiver data
1. The first 8 bits are used to store data
Transmitter -> writes output to the console.
SPIM reads directly from your keyboard