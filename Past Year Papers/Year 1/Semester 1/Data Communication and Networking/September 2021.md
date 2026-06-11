---
aliases:
  - September 2021
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
#### (i)
192.168.1.0
#### (ii)
192.168.1.1 - 192.168.1.254
#### (iii)
30
#### (ii)
25
### b
access-list 1 deny 192.168.1.1 0.0.0.2
int fa0/0
ip access-group 1 in
### c
pc2 -> switch0 -> switch1 -> pc3 -> switch1 -> switch0 -> pc2
### d
The two network are directly connected. When they are directly connect through a router, no configuration is needed.
## Question 2
### a
![[DHCP flow]]
### b
Based on the diagram, both DHCP server 1 and DHCP server 2 have the same ip address pool. Each DHCP server function independently of each other. This means that DHCP server 1 is not aware of the ip addresses offered by DHCP server 2 and vice versa. Because of that PC1 and PC2 
has the possibility of being assigned the same IP address.
### c
*We didn't learn how to configure router as DHCP servers*
### d
*We didn't learn how to configure router as DHCP servers*
## Question 3
*Did not learn this either*
## Question 4
### a
TFBoy -> Router1 -> Router2 -> GameBoy. The router chooses its path based on the vector distance. The router passes the data packet to router2 because it will provide a direct path to GameBoy. This means that the hop count would be just 1. If the router passes the data packet to router3 then to router 2, this means that the hop count is 2. The router choose the path with the least hop count as it assumes that is the shortest distance.
### b
Router1. 
### c
ip route 0.0.0.0 0.0.0.0 30.30.30.2
### d
config t
ip route 40.40.40.0 255.255.255.0 50.50.50.2
### e
The router will do load balancing. This is where the packets are divided into two and both of them are sent through both routers at the same time. OR the router would choose the router with higher link speed. 

# Next Paper
[[Past Year Papers/Year 1/Semester 1/Data Communication and Networking/September 2022|September 2022]]
