---
aliases:
  - Network Security
tags:
  - Notes
  - Cybersecurity
Creation Date: 2023-12-11T11:25:00
Completion: true
obsidianUIMode: preview
---
# Browsers
## Roles of a browser
- A browser has a simple role of displaying content to the user
- Transmitting data from user to browser
## Security issues of browser
- Transmit data from the user to the browser without the knowledge of the user. 
- The browser plugin may contain malicious code or is a malicious program itself
- The browser software itself may be malicious
## Browser attacks
### Key-logger
| Sofware                                            | Hardware |
| -------------------------------------------------- | -------- |
| Program that is installed in the victim's computer | USB drives         |

- Collects and stores the information for future use 
- Transmit the keystrokes over a network connection to the attacker
**See also**: [[Chapter 1 - Information Security Basics#Keyloggers]]
### Man in the middle
A trojan horse inserted between the user and the browser. The attacker will intercept the data being transmitted by the user to the server. The attacker can then use the data to access important financial information of the victim. This is especially dangerous as the server views the attacker as authentic user
### Program Download Substitution
The attacker presents a page with a desirable downloadable program. The attacker also sneaks in a malicious program that the user downloads together
### Page in the middle
Redirecting the user to a fabricated page made by the attacker. The user thinks its real, input their information and the attacker obtains the information

| Man-in-the-middle                | Page-in-the-middle |
| -------------------------------- | ------------------ |
| The attacker intercepts the data | The attacker redirects the user to another page                   |
## Defending against such attacks
| One-time password                               | Shared secret                       | Out-of-band communication                       |
| ----------------------------------------------- | ----------------------------------- | ----------------------------------------------- |
| Both ends should have a list of secret password | Something that only both ends know. | Transmitting two crucial information separately |
| Tokens                                          | Security questions                  | Transmitting credit card and the pin separately | 
# Threats to network communication

| Interception         | Modification              | Fabrication           | Interruption |
| -------------------- | ------------------------- | --------------------- | ------------ |
| Unauthorised viewing | Unauthorised modification | Unauthorised creation | Denying authorised application             |
## Interception
### What makes a network vulnerable to interception
#### Sharing
Networks allow resources and workload sharing which will expose the network to a lot of users.
#### Unknown parameter
One host may be the node of two different network, allowing devices from one network to access resources from devices in another network. 
#### Unknown path
The transmission of data from one host to another may pass through a lot of other hosts. One host may have good firewall and cyber security but another host may have bad security or firewall. 
#### Many points to attack
The transmission of data from one host to another may pass through a lot of other hosts. One host may have good firewall and cyber security but another host may have bad security or firewall. One host does not have control over the access control system of another host. 
#### Complex system
A network usually utilise more than one type of operating system. 
The network operating/control system is more complex than operating system for a single computing system. The attacker may exploit this complexity to launch an attack
#### Anonymity 
An attacker is usually very far away from its target and the attack usually passes through a lot of compromised hosts. So, it is hard to pinpoint the exact location of the culprit.
## Modification & Fabrication
### Threats
#### Insertion
The hacker does not even have to break into the encryption scheme to insert the data. All he has to do is find the right location to insert the data so that it gets encrypted under the same encoding scheme
#### Replay
Reusing data or information that has been transmitted before
**Example:**
A corrupt merchant resubmits a transaction on behalf of another user
#### Physical Replay
Misdirecting the guard by displaying an innocent image on the cctv
#### Sequencing
Reordering the order/permutation of the data
This is common in networking where one fragment of a packet arrives earlier than it is intended. 
The router determines the best route to send the packet to based on the information it has. The router first sends packet A to route 1. Then the router learns route 1 is no longer optimal, sends packet B to route 2; however, turns out, route 2 is better than route 1, causing packet B to arrive first. 
#### Substitution
The attacker replaces a piece of the data stream with another. For example, Amy obtains a copy of two communications, one is to transfer 100 to her account and another is to transfer 10000 to her friend's account. Amy can change her friend's account number to hers so that she obtains both transaction. 
## Interruption 
### Threats
#### Excessive demand
Overloading the server. Sending more command than the server can process. Eventually, the server runs out of resources to process the command. Some servers shut down completely. Some shuts down services to compensate for certain users
#### Component failure
Hardware failure. Usually not caused by attackers from malicious attacks
#### Routing
Routers have to trust one another for status update and accessibility of other parts to the Internet. 
One bad data is enough to poison the data pool of many routers, affecting the flow of data. 
Internet routing protocol has self-healing properties, meaning, the routers will recalibrate to recover from bad data; however, this still takes some time
# Wireless Network Protection
## Wireless Network Visualisation
Access points receives and transmit data between devices known as stations. Each device will have a Network Interface Card, NIC, which will have Media Access Control, MAC address, which is globally unique. 
## Wifi frames
| MAC header | Payload | Frame Check Sequence    |
| ---------- | ------- | --- |
|            |         |     |
## Management Frames
The most important frame as it handles how data.

| Beacon signal                                                                   | Authentication                                                                 | Association request and response                          |
| ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ | --------------------------------------------------------- |
| The beacon signal means the network is ready to accept connections              | A NIC requests a connection by sending authentication frames                   | The NIC wants to establish a session with an access point |
| If you're in a copy shop, your laptop would receive beacon signal from the shop | A computer authenticates by sending its MAC address in an authentication frame | The NIC and the access point exchange information on the parameters of their interaction and capabilities                                                          |
## Service Set Identifier
Authentication of access points. 
## Web Equivalent Privacy, WEP weaknesses
### Static Key
The same encryption key is used a lot of times without changing
### Weak Encryption System
The encryption key is only 40 to 104 bits. Attackers can easily use programs such as WEPCrack or AirCrack-ng to crack a WEP encryption
### Weak Encryption Algorithm
WEP does use RC4 directly for encryption. Instead RC4 is used to generate a random sequence of number from the 24 bit Initialisation Vector and 40 bits key. 
WEP then combines the key sequence with the data using XOR function
### Authentication 
Any device with the correct SSID and MAC address can connect and is assumed as legitimate
### Integrity
If the attacker wants to change part of a communication, the attacker only has to change the data, create a new integrity check and replace the old one with the new one 
### Encryption key
Allows 64 to 128 encryption key but the first 24 bits are from initialisation vector to form RC4 key which can reduce the key itself to 40 bits or 104 bits
## WiFi Protected Access
### Why WPA > WEP
#### Non-Static key
Temporal Key Integrity Program, TKIP is implemented to change the encryption key in each packet header
#### Authentication
Employs Extensive Authentication Program by with authentication can be done using password, token, or certificates
#### Strong Encryption Algorithm
Uses AES as an encryption algorithm
#### Integrity
Includes a 64-bit integrity check that is encrypted
#### Session initiation
WPA has 3 stages when initiating a session
1. Authentication
2. Four-way handshake
	1. Ensures client can generate cryptographic key 
	2. To ensure both parties can generate key for encryption and integrity on both ends
4. Group handshake
### WPA attack
**Man-in-the-middle( ARP spoofing) attack** 
During association, the device sends its credentials to the access point to authenticate and the access point sends a message back. 
The attacker changes its MAC address to that of the access point and sends a dissociation requests to the device. The attacker than changes its MAC address to the now dissociated device and sends an association requests to the access point, disguising itself as the legitimate device
**Blind trusting**
The client has no way to confirm the access point is legitimate or just an attacker disguising itself as the access point
# Denial of Service, DoS
- [i] Denying a device from accessing certain services 
**Possible reasons** 
1. Excessive demand
2. Application failure
3. Disabled communication
4. Hardware failure
**Flooding**
- The attacker sends more command than the server can process
- Eventually the server runs out of memory to store the commands. 
## Blocked Access
1. Modifying access control data
2. Disabling access control data
3. Interfering with the network routing to prevent requests packets from reaching the server
4. Delete permissions for resources
## Attacks
### Ping of Death
One device sends an excessive amount of packets to another device. Most modern device are protected now
### Smurfs
The hacker finds the network of victims. The hacker then changes its ip address to one of the devices in the network so that recipients will send packets back to the victim. The hacker will then send packets through the broadcast address. Since the ip address is one of the devices', every other hosts will send a reply packet to the victim. 
### SYN floods
The attacker sends a lot of SYN request packet to a server and the server replies with SYN acknowledge packet but the attacker never respond to the last SYN-ACK packet. This ties the server up and eventually, the server runs out of resources and is unable to respond to legitimate hosts 
# Distributed Denial of Service, DDoS
The attacker usually controls one or more master controller which controls command and control centres which tells the botnet when to start attacking and when to stop
## First Stage
The attackers first gather its army of zombies/botnets by infecting vulnerable devices. They achieve this by installing trojan horse or when the victim installs malicious program
## Second Stage
The attacker uses the zombies to send a flood of pings to the victim. 
# Firewall 
A collection of security measures to prevent unauthorised access to a computer system.
The firewall is inserted between the premises network and the Internet. This basically forms a parameter and a controlled link. The point of the parameter is to protect the devices in a network from Internet attacks and to produce a chokepoint at which security and auditing can be imposed. 
**Packet:**
1. Accepted
	1. The packet is allowed to go through the firewall
2. Dropped
	1. The packet is not allowed to go through the firewall with no indication of failure
3. Rejected
	1. The packet is not allowed to go through the firewall with indication of failure
**Characteristics of firewall**
1. Every packet has to pass through the firewall 
2. The firewall is impenetrable
3. Only authorised users, defined by the local security policy can pass through the firewall
**Firewall Techniques**

| Direction control                                                                                                      | User control                                                   | Behaviour control                      | Service control |
| ---------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------- | -------------------------------------- | --------------- |
| Determine the direction in which particular service requests can be initialised and allowed to go through the firewall | Controls access to services according to the user accessing it | Controls how certain services function | Determine the type of Internet services that can be accessed, inbound or outbound                |

**Firewall Types**

| Packet filter firewall                                                                                         | Application level firewall                                                                      | Circuit level firewall                                                                                                                            | Stateful Multilayer Inspection firewall                                                                                                                                   |
| -------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| The firewall inspects each packet individually to determine if it should be allowed to go through the firewall | The firewall analyses the application information to determine if the packet is allowed to pass | Essentially only allows one network to be an extension of another. Forms a virtual gateway that limits the number of connections that can be made | Combines the packet filter firewall and application level firewall. Stores the information of packets that are allowed to pass through and use them for future references | 

# Intrusion Detection System
| Pattern - based                                                                                           | Heuristic                                       |
| --------------------------------------------------------------------------------------------------------- | ----------------------------------------------- |
| Relies on pattern matching                                                                                | Based on information that is obtained over time |
| Perform simple pattern matching and report situations with patterns that matches the pattern of an attack | Also known as anomaly build, creates a model of acceptable behaviours and flags exception to them                                                |

## Pattern - based
- Relies on pattern matching
- Good at detecting attacks with patterns:
	1. Ping attacks
	2. Tear drop attacks can only be detected with much of the information has been obtained
## Heuristic IDS
- The actions are categorised into good suspicious or unknown
	- These actions can move between these categories according to how the IDS define them
- Heuristics IDS are limited to the information that they have at the moment

# Next chapter 
[[Chapter 4 - Information Security Best Practices]]