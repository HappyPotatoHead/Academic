---
aliases:
  - September 2023
tags:
  - PYQ
  - Cybersecurity
Creation Date: 2023-12-13T14:07:00
Completion: true
obsidianUIMode: preview
---
# Section A
## Questions 2
### Question A
**DoS** attacks are usually from a single source or computer whereas **DDoS** attacks are usually from multiple sources or multiple computers attacking a victim. **DoS** attacks usually ranges from smurfing, ping of death, and SYN attack but **DDoS** usually include sending bulk emails or massively ping a victim. **DoS** attacks are easier to detect and dealt with whereas **DDoS** attacks are harder to be dealt with. **DoS** or **DDoS** attacks are done to deny a person from accessing services or applications. These attacks can also be done as a form of distraction, making more resources to be allocated to dealing with **DoS** or **DDoS** attacks, allowing other malicious attacks to happen

### Question B
#### Confidentiality
In confidentiality, the data is hidden from any outsider and is not read or intercepted by any unauthorised third party source. Encryption algorithm and hashing algorithm are implemented to encrypt and turn any data unreadable to prevent any outsider from understand the data, protecting the confidentiality. This is important to ensure that only intended and authorised personnel can view the data
#### Integrity 
In integrity, the data has not been modified by an authorised personnel or source. Digital signature are implement to provide integrity. It can help verify if the data has been corrupted or changed by comparing the hash value
#### Authenticity
In authenticity, the data is not fabricated or reused and is verified to be from the authorised sender. Digital signature are implement to provide authenticity. It can help determine the original sender of the information. 

### Question C
![[network_security_model_2|1000]]

The sender sends a data to the sender. The data is first encrypted with a key to form encrypted data. The encrypted data is then decrypted back to the original data before the receiver received it. The key being used can be the same or different depending on whether the encryption algorithm is symmetrical or asymmetrical. A popular encryption algorithm implement is the RSA or AES During the transmission of the data, an attacker or interceptor may steal the data for themselves. 
### Question D
#### Plaintext
Messages or text is can be read by a person
#### Key
The value that is used to change readable text to unreadable text
#### Encryption algorithm
The function that is used to turn plaintext to cipher text
#### Decryption algorithm
The function that is sued to turn cipher text to plain text
### Question E
| Substitution                              | Transposition                                             |
| ----------------------------------------- | --------------------------------------------------------- |
| Set of bits that is exchanged for another | The permutation of the bits is altered                    |
| Changes the identity of the ciphertext    | Does not change the identity of the ciphertext            |
| Example: Caeser cipher                    | Example: Columnar transposition cipher, Rail Fence cipher |
| Does not change the position of the bits  | Changes the position of the bits                                                          |

## Section 3
### Question a
Private key and public key. These key pairs are used in RSA Public key is used for encryption of the data being sent. The sender's private key is used to decrypt the encrypted data. This
### Question b
#### Question i
*Passive attacks are essentially attacks that intercept the data stream but does nothing. Essentially just to view the data. Affecting confidentiality*
Alice and Bob can switch their public keys over the network. They can then use each other's public keys to encrypt the messages. Then, each of them then can use each other's private key to decrypt the messages
#### Question ii
Integrity and Authenticity. The main threat is modification and fabrication of data and information. 
#### Question iii
Through digital signatures 
### Question C
| Dormant                                  | Propagation                                    | Triggering                                                                  | Action |
| ---------------------------------------- | ---------------------------------------------- | --------------------------------------------------------------------------- | ------ |
| The virus is just there and does nothing | The virus began duplicating itself and spreads | The virus transitions from the dormant or propagation phase to action phase | The virus does that it has been created for, executing malicious code|
### Question D
| Interception         | Interruption            | Modification        | Fabrication |
| -------------------- | ----------------------- | ------------------- | ----------- |
| Unauthorised viewing | Blocking authorised use | Unauthorised change | Unauthorised creation            |
### Question E
1. Packet Filter Firewall
2. Stateful Multilayer Inspection Firewall
### Question F
-- 
# Section B
## Question 4
### Question a
1. To collect evidence of a cyber crime
2. To find out the extend of damage done to a computer system
3. To find out what kind of attack it was
4. To find out who launched the attack
5. To find out how to prevent the attack from happening again
6. To understand how the attack happened in the first place
### Question B
| Demonstrative                                                                             | Direct                                 | Documentary                                         | Real          |
| ----------------------------------------------------------------------------------------- | -------------------------------------- | --------------------------------------------------- | ------------- |
| Evidence that comes in the form of models or experiment to prove an event has taken place | Evidence in the form of oral testimony | Evidence that comes in the form of books, documents | Physical evidence that links the culprit to the crime scene |
### Question C
#### SRC
1. **S**ufficient
	1. Enough 
2. **R**elevant
	1. Has connection and ties to the case at hand
3. **C**ompetent
	1. It is useful
#### CAARB
1. **C**omplete
	1. The evidence should be enough to exonerate other suspects
2. **A**dmissible
	1. Can be used in the court of law
3. **A**uthentic
	1. It is genuine
4. **R**eliable
	1. The evidence is relevant 
5. **B**elievable
	1. The evidence is real and possible to be true
### Question d
No. Deleting the files do not actually delete it. Instead, the pointer of the file in the allocation table is deleted. If a new file is saved on the same location but occupies less space, fragments of the original file will persist. The sector that holds the fragments of the data is known as free space. This is because the system marks them as usable when needed. When another file is saved in this sector, it is known as allocated. Unallocated sectors will hold fragments of the data until it is overwritten

## Question 5
### Question a
#### Transfer
Transferring the risk to another asset, process, or organisation. If lacking, an organisation can reach out to other firms or organisations that specialises in security management or administration. The organisation can then transfer the risk associated with managing complex system to the organisation that specialises with dealing these issues
#### Termination
Stopping the company from implement the service that would cause uncontrollable vulnerabilities
#### Acceptance
Accepting the outcome of the exploitation of the vulnerabilities. This is usually done when the asset at risk is not important or not worth the effort
#### Mitigation
Attempt to attenuate the outcome of the attack. 
1. Disaster recovery plan
2. Incident response plan
3. Business continuity plan
#### Defense
The most popular strategy where the companies employ techniques and mechanism to defend against the exploitations
### Question b
#### Question i
*Asks us what a company should do*
The company should isolate the affect files and data from other unaffected data. This prevents the malware from spreading. The company should also restrict access to the data to prevent more people from accessing them, allowing the response team to work with ease. The company should also be transparent and inform those who will be affected to show their commitment and maintain their trust. 
#### Question ii 
1. Start informing the employees on cybersecurity
2. Start training the employees on how to react in case of an attack 
3. Monitor employee's activity
4. Control installation of software
5. Modify the control access of certain data
### Question c
--
### Question D
1. Incident response plan
2. Disaster recovery plan
3. Business continuity plan


