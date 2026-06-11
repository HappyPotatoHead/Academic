---
aliases:
  - Virtual LAN
tags:
  - Notes
  - Data-Communication-and-Networking
Date: 2023-09-18
Completion: true
obsidianUIMode: preview
---
- [!] This topic mainly focuses on commands 
# Creating VLAN
config t
vlan \# -> number
name \[name goes here]

# Showing VLAN List
show vlan br

# Assigning & Removing 
## Assigning
int fa\#/\# --> number
switchport access vlan \#
## Removing
### Removing VLAN from port
int fa\#/\# --> 
no switchport access vlan \#
### Removing VLAN
config t
no vlan \#
- [!] The port is still assigned to the VLAN. It will remained with the VLAN after the VLAN is recreated. 
- [!] The port is *removed* together with the VLAN

# VLAN Spanning
>[!NOTE] DEFINITION
>VLAN spanning is expanding the VLAN network by connected multiple switches. The switches can have the same VLANs
## Trunking
int fa\#/\#
switchport mode trunk

- [!] This command must be done on both switches
## Restricting Trunking
int fa\#/\#
switchport trunk allowed vlan \#, \# - \#
# VLAN Connectivity
1. PCs of the same VLAN can communicate with each other on the same switch
2. PCs of the same VLAN can communicate with each other on different switch
3. PCs of different VLANs cannot communication with each other. 
**Use a router** - one is enough.

int fa0/0 
no ip address 
not shut
int fa0/0.1 --> the .1 is the VLAN 1
encap dot1q \#
ip address 192.168.1.254 255.255.255.0
int fa0/0.2
encap dot1q 2
ip address 192.168.2.254 255.255.255.0
exit

# Benefits of VLAN
1. Cheaper
	1. Do not have to buy as much router and switch as traditional LANs
2. VLAN spanning
	1. Allows user to be in different locations while still connected to their network
3. Increased security
	1. Reduce the risk of broadcast storm attack - Hackers spamming packets and flooding the network until the network device congested, buffered and crashed.
	2. By minimising the broadcast domain, the number of affected host is reduced.
# Next Chapter 
[[Chapter 7 - Access Control List]]