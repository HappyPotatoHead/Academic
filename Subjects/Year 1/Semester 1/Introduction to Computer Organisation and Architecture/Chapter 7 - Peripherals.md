---
aliases:
  - Peripherals
tags:
  - Notes
  - ICOA
Date: 2023-09-18
Completion: true
obsidianUIMode: preview
---
Peripherals = I/O devices
Peripherals is often slower than cpu/processors
There has to be an interface to translate the signals sent by the peripherals to the cpu

# Busses
Wires that carry electrical signals
## Internal Bus
Any bus in processor
## External Bus
Used in I/O interface

## Major components of bus
### Data bus
Carry data from source to destination
### Control Bus
Carry the functional information that defines and controls the current bus activity
### Address Bus
Designate source and destination address of the data
## Interface Unit
Translate the signals between CPU and I/O devices
**3 Internal Registers**
1. Data
	1. Holds the data
2. Command
	1. Tells the controller the type of operation requested by the CPU
3. Status
	1. Check if the I/O device is ready
# Accessing I/O devices
## Memory-mapped
I/O ports are embedded in the memory location. The memory is divided into 2 parts -> the physical memory location and the peripherals
**Used by:** MIPS
**Benefits**
1. There is no special consideration by the processor
2. Writing into I/O memory space is requires no special instructions
**Drawback**
1. It takes up part of the memory address space for I/O mapping
### Typical read cycle
1. CPU places the address to be read from in the address bus
2. Activate memory read control signal on the control bus. 
3. Wait for the memory to retrieve data from the address location and place the data on the control bus
4. Transfer the data from the control bus to the CPU
5. Deactivate the memory read control signal to terminate the reading process

### SPIM INPUT -> Putting information in
#### Receiver control 
1. First bit > ready bit
	1. 1 = new data to be read
	2. 0 = no new data to be read
2. Second bit > Interrupt enable
	1. 1 = interrupt when data is available
	3. 2 = no interrupt when data is available
The rest of the bits are unused
#### Receiver data
8 bits are used to store data
### SPIM OUTPUT > display information to the console
#### Transmitter control
1. First bit > Ready bit
2. Second bit > interrupt enable
#### Transmitter data
8 bits are used for reading
## Isolated I/O
The address space for I/O devices are separate from the main memory. 
**Used By:** x86
**Benefits**
1. Can utilise the main memory completely
**Drawbacks**
1. It is slower
2. Need special instructions
### Typical Reading cycle
1. CPU places the address of the device on the address bus
2. **Determine either to read or write**
	1. IF READ
		1. Wait for memory to retrieve data from the address location and place them on the data bus. 
		2. Reads the data from the data bus
	2. IF WRITE
		1. Writes the data into the data bus
3. Drop the memory read/write control signal to deactivate the reading/writing cycle

# Data transfers
## Programmed I/O
The CPU constantly waits/request on the status of the peripherals.(polling) Think of it like a while loop
**Drawback**
1. It is slow. 
2. CPU must request repeatedly
3. Because it has to constantly check on the device, it is wasting time. The CPU can be doing  something else

**CPU handles data transfer**
## Interrupt I/O
The CPU has the freedom to do its own thing but gets interrupted by the peripherals. While waiting, the CPU does other things but once the device is ready, the CPU drops everything does prioritise the device instead. 
**CPU handles data transfer**
### Example -> INPUT
1. CPU does its own thing
2. CPU receives interrupt signal
3. CPU completes current task
4. CPU stores the next instruction address in address register
5. CPU does the I/O instructions
6. CPU jumps back to the address register
**OUTPUT is basically the same**
## Direct Access Memory (DMA)
Another hardware handles the data transfer. 
**STEPS**
1. The CPU request DMA to handle the data transfer between the main memory and the I/O device
2. DMA issues the right for the I/O device, waits, manages the data transfer between I/O and the main memory
3. DMA interrupts CPU once data transfer is done
**CPU does not handle data transfer**

# Bus arbitration
More than one bus master and request the bus
#### Static bus 
1. Easy to implement
2. Can be predetermined
3. Less efficient
	1. Bus can be assigned even if not needed
4. Does not take need into account
#### Dynamic bus
1. Assigns bus only when needed
2. Each bus master is equipped:
	1. Bus request line
		1. Request for the bus to be given to them
	2. Bus grant line
		1. Receive permission to use the bus

# Data Transmission 
## Parallel Data Transfer
The data is transferred over multiple lines. The entire message is transferred at the same time
Faster and used for short distances
**Problem:** Data skew problem - Bits are transferred at a wrong time
## Serial Data Transfer
The data is transmitted over a single line. The bit is transferred one at a time. Slower and used for long distances. Growing relevance.
### Synchronous Transmission
**Constraints**
1. The devices must be in the same clock rate
2. Expensive 
3. Clock skew problem - cannot be long if they are fast
**Benefits**
1. Data can be sent in chunks
2. More efficient -> less overhead
### Asynchronous Transmission
The data is enveloped with start bit and one or more end bit. There are also gaps between each data.
**Benefits**
1. The devices can be in different clock rates
2. No need for both sender and receiver to be synchronous
**Constraints**
2. There is overhead when transmitting data
## Universal Serial Bus
To retire all serial and parallel ports
**Characteristics**
1. Plug and play
2. Proving power to low-consumption devices
3. Single standardised interface socket
**Benefits**
1. Control peripherals
	1. Allows data to flow in both directions
2. Power distribution
	1. Can be bus-powered
3. Error checking and recovery
4. Power conservation
	1. Enters suspend phase when inactive
5. Expandable through hubs

**Wires:** power, ground, D+, D-
Power wires are to provide power to the peripheral devices
**Logic Values**
if D+ > D-  by  200 millivolts: logic value is 1
If D-  > D+ by  200 millivolts: logic value is 0
### Non Return Zero Inverted (NRZI)
Encoding the data and provide synchronisation between the sender and the receiver. 
**How does it work?**
1. The first NRZI bit is the data bit 
2. If the bit in data is 0, the NRZI is inverted
3. If the bit in data is 1, the NRZI remains
**Problem**
IF the data is all 1, the NRZI does not transit
**Solution**
Stuff in '0' after every 6 bits. Receiver should remove these extra 0 when converting NRZI back to data
### USB Transmission
**3 types of packet**
1. Output Packet
2. Data Packet
3. Handshake Packet
#### SYNC - 00000001
Because it is 0000001. The corresponding NRZI has 7 edges
Used to synchronise the receiving clock rate. To show the beginning of a new packet
#### PID -> Packet identity
Consists of 8 bits
The first 4 bits are for the type of packet. The last 4 is the inverted form of the first 4 in order to error check on the type
#### CRC -> Cyclic Redundancy Check
Calculated from the data at the sender end and the receiver end. If the CRC on both ends do not match, an error exists. The packet will be discarded or retransmitted
#### EOP -> End of Packet
Signifies the end of the packet

### Transfer type
#### Bulk Transfer
1. There is no specific data transmission request. 
2. There is error checking using CRC
**e.g.**
Sending data to printer can be slow without any problems
#### Interrupt Transfer
1. It used for applications that require immediate attention
2. USB uses polling

#### Control Transfer
Used to configure and set up devices
Has 3 stages
1. Setup stage
	1. Convey the type of request to the target device
2. Data stage
	1. This is optional and only used during data transfer. 
	2. If the request is to read the device descriptor, the device will use this stage to send the descriptor
3. Status stage
	1. Check the status of the operation
#### Isochronous Transfer
1. Real-time applications that need constant data transfer
2. There is no error checking since there is no time
### Interrupt and Exception
#### Interrupt 
External events that requires the processor's attention. It is normal and not an error
**Example**
MIPS processors uses syscall to interrupt
#### Exception
Errors that are detected in the processor
1. If the error is un-recoverable, the program is terminated by the OS
2. If the error is minor, the OS or the program itself fixes it

**Underlying mechanism of both interrupts and exceptions are essentially the same**
#### Interrupt processing in MIPS
1. Disable further interrupts
2. Record the cause of the interrupt/exceptions
3. Transfer control over to exception handler
	1. Handler will save the program counter
	2. Current operating mode
	3. Status of interrupt
4. Stores return address

