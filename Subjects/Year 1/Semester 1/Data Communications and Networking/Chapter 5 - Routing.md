---
aliases:
  - Routing
tags:
  - Notes
  - Data-Communication-and-Networking
Date: 2023-09-18
Completion: true
obsidianUIMode: preview
---
# Calculate network address
## Ways
1. Manually
2. IP Calculator
### IP Calculator
Need 2 things
1.  an ipv4 address of any host in the network
2. Network address
**Range of IP address** 
192.168.1.0 ---> 192.168.1.255

- [!] 192.168.1.0  and 192.168.1.255 cannot be assigned to any computer
#### Network address: 
The main address of any network, that is used to represent all devices in a LAN. Most of the time will end with 0
FIRST ADDRESS
#### Broadcast address: 
The last address of any network, is used to send data to everyone. Data that is sent to the broadcast address, the data will be sent to everyone else. LAST ADDRESS

#### First usable address/Host Min:
the 1st address that can be assigned to any hosts  ---> 192.168.1.0 + 1
**Last usable address/Host Max**: The last address that can be assigned to any hosts. 

#### \# of hosts IP: 
How many IP address that you have, that you can assign to the PC. The maximum number of computer in a network. If exceeded, you cannot assign any more IP address
**Formula:** $2^x - 2$
x number of network host
Minus 2 because the network address and broadcast address cannot be used
**Example**
> 192.168.1.0/24 
 maximum number is /32
 /32 - /24 = 8 host bits left
 2^8 = 256 - 2 = 254

> 192.168.2.0/26
> maximum is /32
> 32 - 26 = 6 host bits
> 2^6 - 2 = 62. Minus 2 because the network address and broadcast address cannot be used
> this means only 62 PC can be used

**#** of hosts IP = /32 - /28 = 4 hosts ip
2^4 - 2 = 14 pcs. 
![[Ip information.png]]

# How does it work
When the router receives the data. It checks the routing table to see if the destination network address is available. If yes, the router determines with interface to send the packet to. If no, the router sends the packet to the default route or it will discard the packet and send an ICMP message to the source. 
# How it chooses its route
### Distance Vector/Hopcount
The lower count of router is assumed to have shorter distance. Thus, it goes for the shorter distance vector
### Link speed
Chooses the faster route
### What if they're both the same
The router does load balancing -> 50/50 between the two routes

# Types of Routing & Commands
Since communication is **two way**, the commands must be inserted in **both communicating routers**; **both to and fro.**
## Static routing, S
ip route \[destination network address]\[destination network mask]\[the ip of the next router]
## RIPv4, R
you have to know all connected network addresses to the router for this to work

router rip
network \[network address]
network \[network address] 
## Static routing, S*
This routing is only used as the last resort where the router does not any of the routes in its routing table. 

ip route 0.0.0.0 0.0.0.0 \[the ip of the next router]

# Routing Precedence
Admin distance is prioritised. If they have the same AD, then distance vector/ link speed is considered. 
1. Static routing
2. OSPF
3. RIPv4
4. Default route


# Chapter 6 - Virtual LAN
[[Chapter 6 - Virtual LAN]]