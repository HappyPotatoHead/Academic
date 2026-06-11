---
aliases:
  - Execution
tags:
  - Notes
  - ICOA
Date: 2023-09-18
Completion: true
obsidianUIMode: preview
---
# Major components of a Computer Organisation
1. Control Unit
	1. It needs circuit to 
		1. Decode the instructions 
		2. Issue signals to control the flow of information between data path and other components
		3. Control the operations done by the datapath
		4. Decide the next instruction and obtain them from memory
2. Datapath
	1. Executes instruction based on the control signals given by control unit
	2. Load data and access data from memory
	3. Interconnect the functional units accordingly
3. Memory
4. Input devices
5. Output devices
---
# Execution cycle
1. Instruction Fetch
	1. The processor fetches instructions and data from memory
2. Instruction Decode
	1. The processor decodes the instruction - determine the instruction format, instruction and the registers being used - to determine the control signal to determine the operations that it wants to execute
3. Execution
	1. The data-path executes operations based on the control signals given
4. Memory Access
	1. Read or Writing into memory
5. Write Back
---
# Performance of CPU
## Measurements
1. Response time/Execution time
	1. Time taken for tasks to begin and complete
2. Throughput
	1. The amount of tasks to be able to be completely in a given time
## Factors affecting performance
1. Memory
2. Operating system
3. Peripheralas
4. Compilers
## Challenges
1. Cost
	1. Optimising design and components will also optimising performance
2. Power
	1. Optimise performance while minimising power usage
3. Performance
	1. Optimise performance without increasing the cost and power by too much
## Calculation
**Formula:**
Performance = CPI $\times$ Clock Rate $\times$ Instruction count
- [!] Everything is calculated in seconds
- [i] Change clock rate into seconds
---
# Microarchitecture
## Single-cycle
Instructions are done in one cycle
- [!] The clock cycle is based on the slowest instructions
	- [!] If there are multiple Instructions with different time to complete, there will be idling
- [!] The resources cannot be shared, so there will be duplicates
## Multicycle
Instructions are separated into different segment based on the stages in execution cycle
It avoids idling
More complex controls
## Pipeline
Instructions are separated according to the Execution cycle.
The time is based on the slowest stage in the cycle. 
The succeeding instructions began before the current one has been completed
- [!] Improves throughput but does not improve latency -> more stuff gets done but time taken for each task remains the same.
### Performance
$$T_{c,pipeline} = \frac{T_{c, single\;cycle}}{T_{stages}}$$
**Learn to draw the timing diagram**
### Hazards
1. Structural Hazard
	1. When the resource is used in two different ways for two different functions at the same time
2. Data hazard
	1. Using the register before the newest register value is inserted into register file
		- add \$s1, \$t0, \$t1
		- sub \$s2, $\s1, $\t2
		- The example shows the usages of \$s1 before the "add instruction is finished"
1. Control Hazard
	1. Executes the next instructions before it is decided - caused by branch
		-  bne \$s0, \$s1, loop
		- sub \$t2, \$t1, \$t0
**Solution**
- Add a delay
---
# Memory system and hierarchy
## Hierarchy
1. Cache/ SRAM
	1. Fastest
	2. Supplies most data to the processor
2. Main memory/ DRAM
3. Virtual memory
	1. Slowest 
	2. Largest 
	3. Cheapest
## Memory type
### RAM -> Random Access Memory
 - [!] It is volatile; it loses data when turned off
### ROM -> Read Only Memory
- [!] It is not volatile; it retains memory
Name this way because it was only produced during manufacturing time and when burning fuse. Once written, it cannot be changed
**Example**
1. Flash Drives
2. Thumb Drives
## Principle of Locality
### Temporal Locality
Locality in time
When data is used, it is most likely to be used again.
**How to exploit:** When data is recently accessed, bring the data into higher level of memory
### Spatial Locality
Locality in space
When data is used, the nearby data is most likely to be used
**How to exploit:** When data is recently accessed, bring the nearby data into higher levels of memory
### Taking advantage of Locality
1. Store everything in a disc
2. Copy recently accessed and nearby items from disc to DRAM
3. Copy even more recently accessed and nearby items from DRAM to SRAM
---
# Chapter 7 - Peripherals
[[Chapter 7 - Peripherals]]