---
aliases:
  - April 2021
tags:
  - PYQ
  - ICOA
Creation Date: 2024-05-22T13:26:00
Completion: true
obsidianUIMode: preview
---

## Question 2
### Question b
#### (i)
1. Single cycle
	- Each instruction is done in a single cycle. 
	- The clock cycle timer is set to accommodate the slowest instruction, lw.
		- Even if an instruction is completed, the processor still has to wait for the entire clock cycle to be over before continuing to another instruction
	- The resources cannot be shared
	- Some instructions may not be able to be completed in one single clock cycle
	- This datapath is the slowest
2. Multicycle
	- The instructions are broken down into different stages
	- Each stage take one or more clock cycle to complete
	- The instructions make take different clock cycles to finish
	- The latency and throughput is better than single cycle
	- The resources can be shared and are only allocated when needed
3. Pipeline
	- It executes multiple instructions at the same time. 
	- The next instruction begins even before the current instruction has been completed. 
	- This improves throughput but not latency. 
	- The clock cycle time is set to accommodate the slowest stage in the execution cycle.
	- [!] Has hazards
		1. Structural hazards
			1. When the same resource is being used in two different ways at the same time
			2. two resources try to read the same memory at the same time. 
		2. Data hazards
			1. The value in register is being used before it is saved into the register file
			2. add \$s0, \$s1, \$t0
			3. sub \$s2, \$s0, \$t1
		3. Control hazards
			1. The next instructions begins even before it has been decided.
			2. Caused by branching
			3. beq \$0, \$s0, ELSE
			4. addi $t0, \$0, 5
#### (ii)
Refers to the preservation of the values in registers when calling a function or a subroutine. The caller-saved registers are usually not reserved but the callee-saved registers are usually reserved to maintain data integrity. 

## Question 3
### Question a
#### (i)
![[Instruction formats|500]]
Instruction A uses I format, instruction B uses R format, instruction C uses J format
The opcode in R format is always 0 and the function field determines the type of instruction that it will carry out. The opcode and I and J format determines the type of functions that it will carry out. R format uses 3 registers whereas I format uses 2 and J format does not use any registers but instead use labels and addresses. Instruction A is slower than Instruction B since lw has to access the memory which is slower than accessing registers. Instruction A has to determine the address in memory whereas, instruction B only uses the values in the registers. Instruction C is the slowest as it may have to fetch target instructions from another memory location
#### (ii)
Good design demands good compromise. The instruction lengths are similar in size but different formats. The instructions are support memory access
### Question b
| Similarities                              | Differences                                      |
| ----------------------------------------- | ------------------------------------------------ |
| Both of them uses registers               | Instruction A require memory access              |
| The length of opcode are the same, 6 bits | Instruction B does not have any immediate values | 
### Question c
1. It is more complex than statically linked library as it updates automatically
2. More overhead time
	1. It needs time to find and link the library that it needs
3. Version compatibility
	1. Multiple applications rely on the same DLL. If there are any updates on the DLL, it may affect the applications. If the new DLL version is not backward compatible, the applications that use the DLL may break or have unpredictable behaviour.
## Question 4
### Question b
#### (i)
Used to assign busses to bus masters. More than one bus master can request the bus line
#### (ii)
Static mode
1. Can be predetermined
2. Easy to set up
3. Does not take need into account
4. Assigns the bus even when not needed 
Dynamic mode
1. More complex
2. Only assigns bus when it is required
3. Each bus master has a bus grant line and a bus request line
	1. Sends bus request line if the bus master requires the bus
	2. Before it can use the bus, it must have permission to use it through bus grant line
### Question c
1. Interrupt driven I/O
	1. The CPU is free to do its things while it waits for the device to be ready
	2. The CPU does the data transfer
	3. STEPS:
		1. The CPU receives the interrupt signal
		2. The CPU completes the current instruction
		3. The CPU saves the address of the next instruction
		4. The CPU completes the instructions by the interrupt
		5. The CPU jumps back to the saved address
2. Programmed I/O
	1. The CPU constantly waits for the peripheral device to be ready. This is called polling
	2. CPU does the data transfer
	3. The CPU has to constantly send request as not to miss out anything important so it cannot do much while waiting.
	4. It is very slow
3. DMA
	1. Direct Memory Access
	2. The CPU does not do the data transfer
	3. Requires a special hardware to do the transfer
	4. The CPU requests the DMA to do the data transfer
	5. The DMA requests control over the peripherals and does the data transfer
	6. The DMA issues interrupt signal to the CPU once it is done. 