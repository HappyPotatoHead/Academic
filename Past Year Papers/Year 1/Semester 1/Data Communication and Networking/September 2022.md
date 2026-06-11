---
aliases:
  - September 2022
tags:
  - PYQ
  - Data-Communication-and-Networking
Creation Date: 2024-05-22T13:26:00
Completion: true
obsidianUIMode: preview
---
# Section A
## Question 1
### a
2 network. The computer is connected to both ethernet and wireless connection. 
### b
#### (i)
192.168.68.255
#### (ii)
192.168.68.0
#### (iii)
192.168.68.2 - 192.168.68.254
### c
Hub. The hub can placed between the PC and the router. The hub can act as an amplifier that amplifies the signal so that it can be transmitted over a longer distance. A hub broadcast the data packet that is received.
### d
Before the lease expires, the pc will send a request to the DHCP server to request that the same ip address is assigned to it. DHCP servers also have address reservation feature. This means that the same ip address will always be assigned to the same mac address. 
### e
10,000 Mbps
### f
![[DHCP flow]]
#### Discovery packet
The new device will send the DHCP discover packet to the broadcast address. This means that every device on the network is going to receive the DHCP discover packet which contains request for IP address  and other configuration parameters.
**Source IP:** 0.0.0.0
**Destination IP:** 255.255.255.255 
#### Offer packet
The DHCP receives the DHCP offer packet and replies with a DHCP offer packet containing the IP address and other parameters.
**Source IP:** 1.1.1.1
**Destination IP:** 255.255.255.255
#### Request packet
The client receives the DHCP offer packet and replies with a DHCP request packet to request that the IP address and other parameters be assigned to it.
**Source IP:** 0.0.0.0
**Destination IP:** 255.255.255.255
#### Acknowledgement packet
The DHCP server sends DHCP acknowledgement packet to the device to confirm the assignment of IP address and other parameters to the device.
**Source IP:** 1.1.1.1
**Destination IP:** 255.255.255.255
## Question 2
### a
VLAN is cheaper than LAN. There is lesser switch to be bought. 
VLAN is safer than LAN. VLAN minimises the risk of broadcast storm attack. Broadcast storm is where hackers spam packets and flood the network until the network device becomes congested, buffered, and crash. When the broadcast domain is minimised, the number of host affected is reduced. 
VLAN spanning allows user to be connected to the network even if they are in different location.
### b
#### i
yes
#### ii
yes
#### iii
no
### c -> the answer is in the question
There is an IP address conflict. Since both DHCP server 1 and DHCP server 2 has the same IP address pool, there is a chance that both PC is assigned the same IP address. Because of this, the traffic intended for PC1 may be sent to PC2. Furthermore, there packet meant for PC1 may be sent to PC2 
### d
*didnt learn DHCP command*
## Question 3
### a
router rip
network 200.200.100.0
network 200.200.200.0
network 200.200.300.0
network 192.168.1.0
### b
All the paths will be used. The router will do load balancing. The data packet will be divided to traverse the 3 paths. This is because, all the routers are configured with RIPv4. This means that there is no other paths that takes priority. The packet also has to go through a minimum of 2 router to reach ROSE. This means that the packets will be sent at the same time in each route. 
### c
192.168.2.0/24 [1/0] via 200.200.100.1. The static route will be taken. This is because the admin distance of static route is lower than the RIPv4 routes. The hop count is also 0 (*This is because you specify yourself where the data packet is going to go. so there is no intermediate routers*)
### d
Router1 sends the ICMP message. When the router receives the data, it checks the destination network address to see if it exist.  The network address is not in the routing table of Router1. Router1 does not have any default route for the packet to be forwarded to. So it sends an ICMP error message to LISA. 

### e
config t
ip route 0.0.0.0 0.0.0.0 200.200.100.1
# Section B
## Question 4
*WE DID'NT LEARN TCP HEADER*
## Question 5
### Question a
#### (i)
10,000 Mbps
#### (ii)
### Question b
Bandwidth is the maximum amount of data that can be transmitted in a given amount of time. Throughput is the actual amount of data that can be transmitted in a given amount of time. This can be caused by congestion, wrong types of cable and network interface device.  For example, an ISP pay promise a certain amount of bandwidth to a user but the user only experiences a smaller amount of bandwidth
### Question c
![[DNS flow|1000]]
### Question d
![[DNS poisoning|1000]]