---
aliases:
  - ACL
tags:
  - Notes
  - Data-Communication-and-Networking
Date: 2023-09-18
Completion: true
obsidianUIMode: preview
---
# 7.1 Standard Access Control List
## 7.1.1 Manually
config t
access-list \[id] \[permit/deny] host\[ip addresss]
access-list 1 permit any

There is an invisible access-list 1 deny any in the end. access-list 1 permit any counter-acts that 
**Example**
access-list 1 deny host 192.168.1.1
access-list 1 permit any

## 7.1.2 Wildcard
This uses the wildcard mask, which is the opposite of subnet mask
config t
access-list \[id] \[permit/deny] \[ip address] \[wildcard mask]

**Example**
config t
access-list 1 permit 192.168.1.1 0.0.0.255
access-list 1 permit any

The example above allows all devices connected to the subnet.

### 7.1.2.1 How to calculate devices allowed under a wildcard command?
1. Change the wildcard mask into binary
**Example**
0.0.0.255 -> 0000 0000. 0000 0000. 0000 0000. 1111 1111

2. Change the IP into binary
**Example**
192.168.1.1 -> 1100 0000. 1010 1000. 0000 0001. 0000 0001

3. Match the IP and wildcard mask together. If the wildcard mask is 0, the IP remains, if the wildcard mask is 1, the IP changes to x
**Example**
0000 0000. 0000 0000. 0000 0000. 1111 1111
1100 0000. 1010 1000. 0000 0001. 0000 0001
1100 0000. 1010 1000. 0000 0001. xxxx xxxx

4. The x can be represented with either 0 or 1. 
**Example**
1100 0000. 1010 1000. 0000 0001. xxxx xxxx -> this means that any device will be able to communicate

access-list 1 permit 192.168.1.1 0.0.0.255

### 7.1.2.2 How to reverse this?
1. Determine the ip addresses involved
**Example**
PC1 -> 192.168.55.1 PC2 -> 192.168.55.3
2. Convert them into binary
**Example**
PC1 -> 1100 0000. 1010 1000. 0011 0111. 0000 0001
PC2 -> 1100 0000. 1010 1000. 0011 0111. 0000 0011
3. Find the similar bits between them. If it is the same copy them, if it is not, change to x
**Example**
PC1 -> 1100 0000. 1010 1000. 0011 0111. 0000 0001
PC2 -> 1100 0000. 1010 1000. 0011 0111. 0000 0011
		   1100 0000. 1010 1000. 0011 0111. 0000 00x1
4. The result that you get is the combination of the wildcard mask and the IP. By referring to the properties of wildcard mask; if it is x, the bit is 1, if it is not x, the bit is 0.
**Example**
1100 0000. 1010 1000. 0011 0111. 0000 00x1
*Wildcard mask* - 0000 0000. 0000 0000. 0000 0000. 0000 0010
5. Since x can be both 0 or 1. choose the lowest possible value for the IP address.
**Example**
*IP address*        - 1100 0000. 1010 1000. 0011 0111. 0000 0001

access-list 1 permit 192.168.55.1 0.0.0.2

### 7.1.2.3 How to know which device is blocked or permitted
1. Repeat 7.1.2.3
**Example**
access-list 2 permit 172.16.1.3 0.0.0.252
1010 1100. 0001 0000. 0000 0001. XXXX XX11
2. Compare the IP address to the result. Checks if they match. If it does not, reject it.
**Example**
1010 1100. 0001 0000. 0000 0001. 0000 0101 -> 172.16.1.5
1010 1100. 0001 0000. 0000 0001. XXXX XX11
1010 1100. 0001 0000. 0000 0001. 0000 01\[wrong]1 -> rejected

1010 1100. 0001 0000. 0000 0001. 0000 0101. 0011 0011 -> 172.16.1.51
1010 1100. 0001 0000. 0000 0001. 0000 0101. XXXX XX11
1010 1100. 0001 0000. 0000 0001. 0000 0101. 0011 0011 -> Matches = permitted



# 7.2 Extended Access Control List
the id is 100 - 199 / 2000 - 2999
**Command**
config t
access-list \[id] \[permit/deny] \[protocol] \[source IP] \[destination IP] via \[domain name/ port number]
**Example**
access-list 100 deny icmp any any -> deny any device from pinging anyone
access-list 100 deny tcp any any via http

# 7.3 Placing/Removing Access Control List
Placing the ACL depends on where the data is coming from. Sending a data will always have a response.
### 7.3.1 Placing ACL
**Command**
config t
int fa0/0
access-group \[id] \[in/out]
### 7.3.2 Removing ACL
config t
int fa0/0
no access-group \[id] \[in/out]
# 7.4 Deleting Access Control List
- [!] When you delete ACL, the interface is still bound to the access-list
no access-list \[id]

# 7.5 Named ACL (only in CISCO)
## 7.5.1 Standard
config t
ip access-list \[standard \[name]
\[permit/deny] \[source IP/any] \[destination IP/any]
## 7.5.2 Extended
config t
ip access-list \[standard/extended] \[name]
\[permit/deny] \[protocol] \[source IP/any] \[destination IP/any] via \[name / port number]

# Chapter 8 - Packet Analysis
[[Chapter 8 - Packet Analysis]]