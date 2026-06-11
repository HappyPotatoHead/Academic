---
aliases:
  - Disaster Recovery
tags:
  - Notes
  - Cybersecurity
Date: 2023-12-11
Completion: true
obsidianUIMode: preview
---
# Computer Forensic
## Purposes of investigating and analysing a computer system
1. Compliance to company's policy
2. The device has been compromised
3. There has been a violation of law
## Types of Data
1. Persistent Data
	1. Data that remains even after the machine or system has been unplugged/shut off
	2. USB drives
	3. SSDs
2. Volatile Data
	1. Data that is deleted after the system has been shut off
	2. RAM

# Evidence
Comprises documents, verbal statements and material objects admissible in the court of law
## Standards/Characteristics of evidence
### Standards - SRC -> Student Representative Council
1. **S**ufficient
	1. The evidence must be enough 
2. **R**elevant
	1. The evidence must be related to the case 
3. **C**ompetent
	1. The evidence must be convincing and concrete
### Characteristics - CAARB -> CARB
1. **C**omplete
	1. The evidence must exonerate a suspect 
2. **A**dmisible
	1. Can be used in court of law
3. **A**uthentic
	1. Not fabricated/genuine
4. **R**eliable
	1. No question about the authenticity
5. **B**elievable
	1. The evidence does not seem fabricated/feasible
## Types of evidence
1. **D**ocumentary
	1. Evidence in the form of documents
2. **D**emonstrative
	1. Evidence in the form of models or experiments to imitate a scene of crime to prove the occurance of a crime
3. **D**irect
	1. Oral testimony that proves a specific fact
4. **R**eal
	1. Physical evidence that links suspect to the scene of crime 
## Identifying evidence
### Storing and labelling an evidence
- Evidence must be labelled and stored properly to avoid any tempering and makes it easier to refer to in the future.
- Any noticeable mark, damage, number, model number must be noted down. 
- Make sure that the labels are not easily removed
- Make sure to be methodical when collecting evidence 
	- Avoid collecting alone
- Make sure to collect evidence as soon as possible to avoid the culprit from destroying or tempering with the evidence
- Requests log as soon as possible 
- Take photos or videos on the hardware before being taken in for analysis
### Acquiring evidence
| Leave the computer on                                                                                                        | Switch the computer off                                                                              |
| ---------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| The culprit may have left software bomb in the system that will execute commands, delete files or shutting down the computer | Experts argue that this will freeze the state that the computer is in                                |
| The culprit may anticipate investigation and altered the system's binary files                                               | This will result in the loss of data and the loss of data on the RAM                                 |
|                                                                                                                              | Even if this is the best approach, if the server is the one affected, it is unlikely to be shut down | 
### Protecting evidence
- The evidence should be protected and defended against any electromagnetic and mechanical damages
- The evidence should be protected from any form of tempering
- The evidence should be protected against cold, hot, humidity, water, and vibration
- Use static-free evidence gloves when collecting evidence
### Storing evidence
- The evidence should be stored in an closed and controlled environment/room
- Store in a cardboard box, static free bags 
### Analysing evidence
- Analysis should be done in a system designed specifically for forensics
- Analyse a copy of the system and not the original one
	- Analyse a version as close to the original one
- Analyse in a controlled and closed environment
- Log any changes made
- Have strong physical security too
- DOS should be used to do image processing instead of windows unless there are specific tools to take forensic images on windows
- Minimal software should be installed to avoid infection from viruses, trojan horses or other malwares. 

# Free space & Slack space
## Free space

When a file is deleted, it is not actually deleted. Instead, the pointer from the allocation table is deleted. When a second file that is stored in the same sector does not occupy the same space, fragments of the original file exists. The sector that store these fragments are known as free space because the operating system marks them as resuable when needed. When the system stores something else in this sector, it is known as allocated. Unallocated sectors will still hold the original data until the system overwrites them. 
## Slack space
It is the leftover space that happens when the application does not occupy as much space as the system allocated for them. 
Attackers can hide malicious code, tools etc in these slack space or free space. 
# Hash/Message Digest
Hashing tools or algorithms can be used to hash the log files or evidence. The tools or algorithms use should be recorded along with the hash value. Should the investigator prove that the evidence has not been altered, he can do so easily.
# Steganography
The act of inserting information in an image. It is used to bypass security checks or hide information in plain sight
**Tools**
1. WinHex
2. HxD
# Watermarking
Watermarks are used to verify the identity or authentication of the original owner or the author of a project, art, audio, etc. The process of embedding information that links the author to the project itself. 
1. Images
2. Audio
3. Markings
# Key aspect of Computer Crime Act 1997
**Definition:** [[Chapter 4 - Information Security Best Practices#Computer Crime Law|Computer Crime Act 1997]]
## Offense and Penalties
Defines what actions are considered as unlawful and are crimes
- Unauthorised access to computer
- Unauthorised deletion/modification of files
- Spreading malwares
- Cyber frauds
- Hacking
- Identity theft
## Law Enforcement powers
Grants law enforcement agencies the authority to:
1. Investigate computer crimes
2. Obtain search warrants
3. Seize digital evidence
4. Compel cooperation from suspects or individuals that are involved in the cyber crime
## Data Privacy and Protecting
Details how individuals' data would be protected and how or ensures personal information should be handled appropriately in a cyber crime situation

[[Chapter 6 - Legal and Ethical Issues]]
