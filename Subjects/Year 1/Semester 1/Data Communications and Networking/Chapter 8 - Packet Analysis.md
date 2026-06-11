---
aliases:
  - Packet Analysis
tags:
  - Notes
  - Data-Communication-and-Networking
Date: 2023-09-18
Completion: true
obsidianUIMode: preview
---
# Packet analysis
1. Wireshark - automatic way
2. Manual analysis - IPv4
	1. When data is corrupted 
		- Wire shark cannot automatically read it
![[Ip header.png]]
every row is 32 bits segmented into 4 bytes --> like an ip address

header hex stream will be given. The value is in hexadecimal
Answer the question based on the header hex stream

4500049f0000400040060000c0a80071797b1d83
Every hex value is 4 bits
AB = 8 bits = 1 byte
2 characters of hex value is 1 byte

Header length size depends on the file 
--> tells us how big is the header in terms of byte

TOS/DSCP --> Type of service / Differentiated Services Code Protocol

Example: 
Packet #1 : Netflix ( streaming service, fast ) > this is chosen to be processed first
Packet #2: Email ( gmail )
How does the router decide? 
Which packet has more priority
This is not used all the time
If not used it will be all 0

Flags -> As required by the network resources, if IP Packet is too large to handle, these ‘flags’ tells if they can be fragmented or not. In this 3-bit flag, the MSB is always set to ‘0’.

IP flags -> binary

{reserved} {Do not fragment} {More fragments}
The first one is always 0.
**Do not fragment**. If 1 - it is true. if 0 - it is false
If *Do not fragment is 1* --- This packet is NOT fragmented
If *Do not fragment is 0* --- This packet is fragment
**More fragments**. IF 1 - true(more fragment is coming). IF 0 - false(LAST fragment)
More fragment is coming means more packets are still coming
Last fragment it is the last fragment
Think about queue

TTL - time to leave 
This is to avoid looping in the network. Each packet is sent with some TTL

Protocol = what is the next layer protocol

Header checksum this field is used to keep checksum value of entire header which is then used to check if the packet received is error-free
![[Chapter 8 - Diagram]]