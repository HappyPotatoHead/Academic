---
aliases:
  - The Internet
tags:
  - Notes
  - Data-Communication-and-Networking
Date: 2023-09-18
Completion: true
obsidianUIMode: preview
---
# Wired and Wireless connection
## Wired
1. It is faster 
	1. There is a dedicated and direct channel between the devices
2. Less convenient
	1. There is a need for physical cables
## Wireless
1. It is not as fast 
	1. Prone to interference in a crowded area with a lot of devices
	2. There's a limited bandwidth to be shared amongst users
2. It is more convenient
	1. There is no physical cables
# Network metrices
## Bandwidth
It is the maximum amount of data that can be transmitted over a given amount of time
## Throughput 
The maximum amount of data that is actually being transmitted over a given amount of time
## Latency
The total time taken for data to be transmitted from source host to destination host back to source host
# Factors affecting internet speed
**Cable types**
Cat 5, 5e, 6 provides max speed of 1000 Mbps
Cat 6a, 7 provides max speed of 10,000 Mbps
**Network interface devices**
1. Ethernet - 10 Mbps
2. Fast Ethernet - 100Mbps
3. Gigabit Ethernet - 1000 Mbps
**ISP promises**
Only provides 80% of internet speed
**Interferences**
Wireless signal drops/attenuates in a crowded area
Wired connection deteriorates when travelling over a long distance
**Wireless Connections**
820.11b -> 11 Mbps
820.11a -> 54 Mbps
820.11g -> 54 Mbps
820.11n -> 600 Mbps
820.11ac -> 6.8Gbps
820.11ax -> 10 Gbps
# Addresses 
## Ip address 
IPv4 -> 4 bytes -> 32 bits
1. Public IP
	1. Used by devices in a LAN to communicate between devices in another network
	2. It is unique from network to network
2. Private IP
	1. It is unique between devices in a LAN
	2. It is used to communicate between devices in LAN
## MAC address
Physical location of the NIC - network interface card
Unique globally
Used to identify devices in a local area network by the switch
6 bytes of data
- First 3 is vendor id
- Last 3 is its unique id 
## Port numbers 
2 bytes - 16 bits - 65536 unique combinations
0 - 1023 -> server port
1024 - 65535 -> client port
Changes based on the developer and devices
Used to determine the location of application on a device
## Related Chapters
[[Chapter 3 - Network Services]]
[[Chapter 5 - Routing]]
[[Chapter 6 - Virtual LAN]]
[[Chapter 7 - Access Control List]]
# Chapter 2 - Local Area Network
[[Chapter 2 - Local Area Network]]