---
aliases:
  - December 2022
tags:
  - PYQ
  - Cybersecurity
Creation Date: 2023-11-29T13:57:00
Completion: true
obsidianUIMode: preview
---
# Section A
## Question 1
### Question A
![[symmetrical_cryptography|1000]]
### Question B
$$C = 12 ^ 5\;mod\;63$$
$$=45$$
### Question C
One of them is row, another one is column
U  s  i   s  l  v n  l   f   t w p  v m w
### Question D
$$C = (26+26+32+10)^6$$
$$6.90\times10^{11}$$
### Question E
1. Fingerprint
2. DNA
3. Face recognition
4. Iris recognition
## Question 2
### Question A
1. Use archiving and logging tools
	1. This can be used to trace the employee's activity while on the company's network
	2. This can also be used to recover lost data 
2. Monitor employee's activity
	1. Supervise employees and take note of any actions that are suspicious
3. Limit software installation
	1. This can avoid the spreading of malware
4. Limit authority and permissions 
	1. The employees can only access certain files while keeping the important ones out of reach
5. Conduct analysis on staff's company device
	1. This can allow the company to detect any malicious activities before it was too late
6. Strengthen company's policy and punish those who do not follow
	1. The company should strengthen the information policy, backup policy, security poly, and more
	2. This can prevent any staff from attempting an insider attack due to the consequences
	3. This also make the system easier to be recovered
### Question B
1. Dormant phase
	1. The virus does not do anything in this phase. It just exists
2. Propagation phase
	1. The virus begins replicating itself
3. Triggering phase
	1. The virus transitions from the dormant or propagation phase to the action phase
4. Action phase
	1. The virus does what it was intended to do. It starts executing the malicious commands
### Question C
#### Question I
*10 character*
-rwx------
*octal notation*
700
#### Question II
chmod 770
-rwxrwx---
770
#### Question III
chown Nuriyah ProjectX
## Question 3
### Question A
1. DDoS and DoS
	1. Ping attacks aim to deny the services from users.
	2. It may also serve as a distraction
	3. DDoS attacks have similar patterns and format. This makes it easy for pattern-baed IDS to detect
4. Virus
	1. Virus are malware that is capable of executing malicious code on the victim's computer. 
	2. Viruses can spread and propagate but with the help of a human
5. Trojan Horse
	1. It is a program that disguises itself as something desirable and innocent. 
6. Worm
	1. Worms are malware that is able to propagate without the help of a human
	2. It may be carrying a payload
### Question B
### Question C
--
### Question D
1. Use WPA instead of WEP
	1. WPA is more secure and advanced than WEP
2. Implement strong firewall
	1. The firewall should not be able to be easily penetrated any every packet has to go through the firewall
3. Use Demilitarised Zone
### Question E
#### Question I
access-list 1 deny host 192.168.2.1 host 192.168.3.1
access-list 1 permit any any
access-group 1 in/out
#### Question II
access-list 2 permit any host 192.168.3.1
#### Question III
access-list 100 deny icmp any host 192.168.3.1
access-list 100 permit any any

## Question 1
### Question A
-- 
### Question B
$p = 7 \; q = 9 \; e=5 \; d = 4 \; M = 12$
$C = M^e \; {mod}\;N$ 
$$# Section A
## Question 1
### Question a
## Question 2
## Question 3
# Section B
## Question 4
## Question 5$$
$$C = 12 ^ 5 \; mod \; 63$$
$$C = 45$$
### Question C
*Plaintext = row*
*Key = column* 
N e  v  e  r  E v  e  r  G  i  v e U p
H O N O U R S H O N O U R S H
U  s  i   s  l  v n  l   f   t w p  v m w

![[vigenere_table.png]]

### Question d 
--
### Question e
**Characteristics of biometric identifiers:**
1. Universality
	- Everyone has it
2. Distinction
	- Can distinguish everyone from one another
3. Permanence
	- Does not change drastically over time
4. Collectability
	- Easy to gather and collect
**Examples:**
- Fingerprint
- Facial recognition
- DNA
## Question 2
### Question a
1. Monitor employee's behaviour
2. Use archiving and logging tool
3. Control the software download on any company computer
4. Limit authority and permission
5. Physically secure critical systems
### Question B
**Dormant phase**
- The virus remains dormant and does not do anything
**Propagation phase**
- The virus begins duplicating itself
**Triggering phase**
- The virus transitions from dormant phase or propagation phase to action phase
**Action phase**
- The virus does what the action it was made for, payload
### Question C
#### Question i
-rwx------
700
#### Question ii
chmod 770 ProjectX
-rwxrwx---
770
#### Question iii
chown Nuriyah ProjectX
## Question 3
### Question A
1. Ping of Death
	- An attacker sends a long of ping to the victim from a single source
3. SYN Flooding
	- The attacker sends a lot of SYN request packet to the victim. The server replies with SYN ACK packets but the attacker does not reply to the last packet. This ties up the server and eventually the server runs out of resources to reply to valid SYN packets
4. Virus
	- Malicious code that is capable to modify files and programs to replicate itself. It usually requires human assistance to replicate. 
5. Trojan Horse
	- Program that disguises itself as something desirable but does something malicious in the background
6. Worms
	- Malicious code that propagate without human assistance
### Question B
--
### Question C
--
### Question D
Use strong encryption algorithm: AES
Use dynamic key and not static key. Implement Temporal Key Integrity Program where the key changes automatically in each program.
### Question e
#### Question i
access-list 10 deny host 192.168.2.1
access-list 10 permit any 
#### Question ii
access-list 20 permit any
#### Question iii
access-list 100 deny icmp any host 192.168.3.1
# Section B
## Question 4
### Question A
1. Malaysian Communication and Multimedia Commission
	1. Monitor, supervise and regulate multimedia activities
2. MBOT
	1. Give professional recognition to technologists and technicians in Malaysia
3. Cybersecurity Malaysia
	1. Enhance and maintain Malaysia's cybersecurity
	2. Research
	3. Computer forensic
	4. Cryptographic development
### Question B
$$Risk = 1.0*60 - (60*0.07)+(60*0)$$
$$60-4.2+0$$
$$55.8$$
### Question C
#### Transfer
The process of transferring risk to another asset, process or organisation. If lacking, an organisation can reach out to a firm or organisation that specialises in security management or administration. The organisation can then transfer the risk associated with complex security management to the organisation that specialises in that.  
#### Terminate
The business is advised to not implement the service that will cause uncontrollable vulnerabilities or risks.
#### Acceptance
The company accepts the outcome of the exploitation of the vulnerabilities. This is usually done when the asset at risk is not important 
#### Mitigate
The attempt to attenuate the effects or impact of the exploitation. Three plans are used, Disaster recovery plan, Incident response plan and business continuity plan
#### Defence
The most popular option where countermeasures and techniques are put in place to defend against the exploitation. 
### Question D
Information policy
Defines what information is considered sensitive and what to do to protect them. It defines which group of people can view certain information. For example, lecturers can view more information than students 
Backup policy
Defines how and how often backups are executed. Usually, full back ups are done once a week followed by incremental back ups every other day. 
## Question 5
### Question A
1. To gather evidence that is admissible in the court of law
	1. Some data on the computer where the attack was launched or the data on the victim can be used as prove to persecute the culprit
2. To find out what kind of attack that was done and the extend of the damage
	1. This can help understand what was the vulnerabilities and how to prevent them from happening in the future
3. When there has been a violation of law
	1. The computer may have been spreading malware or a part of a cyber-crime
### Question B
1. Documentary
	1. Evidence in the form of documents, books, logs
2. Direct 
	1. Oral testimony that proves a specific fact
3. Demonstrative
	1. Evidence in the form of experiments or models that prove an event did occur
4. Real
	1. Physical evidence that directly links the suspect to the crime
### Question C
**SRC** -> standards
1. Sufficient
	1. The evidence must be enough to answer the questions about the crime
	2. Enough to exonerate other suspects
	3. Convincing
2. Relevant
	1. The evidence must be related to the crime and not out of topic
3. Competent
	1. The evidence must be qualified
**CAARB** -> Rules
1. Complete
2. Admissible
3. Authentic
4. Reliable
5. Believable
### Question D
No. When files are deleted, it is not actually deleted. Instead the pointer in the allocation table is deleted. When another file is stored in the same location but occupies lesser space, fragments of the original data remains. The sector that contains these fragments are known as free space as the operating system marks them as reusable when needed. When another file is stored in the sector, is is known as allocated. Unallocated sectors holds the original data until it is overwritten. 