---
aliases:
  - Local Area Network
tags:
  - Notes
  - Data-Communication-and-Networking
Date: 2023-09-18
Completion: true
obsidianUIMode: preview
---
>[!QUESTION] Definition
> Local Area Network is a group of devices and computers that are connected in a limited geographical area such as building, offices, or home. 

# Networking Devices
## Switch
### Characteristics
1. Used to connect devices in a LAN
2. Understands MAC Address
	1. Has a forwarding table that connects the MAC addresses of the devices connected to the corresponding port. 
3. Unicast 
	1. Sends data packets it receives to only one destination
4. 8, 16, 24 ports
5. Cheaper than router
Switches are generally faster than a router since it is designed for data transmission of data packets within the same network
### How does it work?
1. Receives the data packet.
2. Examines the data packet header that contains the destination MAC address
3. Refers the forwarding table/MAC address table
4. Determines the corresponding port
5. Sends the data packet only to that port
## Router
1. Used to connected devices across networks
	1. No router no WIFI
2. More expensive
3. Understands IP addresses
## Hub
1. Understands neither IP addresses nor MAC addresses
2. Broadcast device
3. Used to connect devices in a same LAN 
4. Less secure
	1. Replaced by Switch
# Cables and connections
## Serial cables
Used to connect devices that uses serial communication protocol. The cables usually have a 9 pin or 25 pin connectors on each end. They transmit data one bit at a time over a single communication channel or line. It is used to connect devices that are close to each other such as in the same room or on the same desk. 
**Mainly used** for connecting one router with another router.
## Console cables (Roll-over cables)
Used to connect devices to networking devices such as router or higher-level switches. 
**Mainly used** for configuration of the networking device.

## Ethernet cable 
1. Ethernet cable - 10Mbps
2. Fast ethernet cable - 100Mbps
3. Gigabit ethernet - 10000MBps

# Chapter 3 - Networking Services
[[Chapter 3 - Network Services]]