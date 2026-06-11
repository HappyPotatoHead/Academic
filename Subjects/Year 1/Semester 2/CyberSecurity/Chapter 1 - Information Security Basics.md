---
aliases:
  - Information Security Basics
tags:
  - Notes
  - Cybersecurity
Date: 2023-12-09
Completion: true
obsidianUIMode: preview
---
# Attacks
## Eavesdropping
The act of listening in on a person's conversation that you're not a part off
## Shoulder-surfing
Watching a person's device over their shoulder without their knowledge
## Wiretapping
Connecting a listening device to a wire to listen in on a person's conversation. The attacker does this by attaching a second wire to the main wire so the data flows through both wires to the intended receiver and the attacker
## Signal Emanations
Reconstructing displays from the visible light reflected off walls or reflective surface. 
Capturing radio frequencies to recreate what was being displayed.
## Acoustic Emanations
Capturing the sound of keys being pressed which the attackers can use to trace the keys being pressed. 
## Keyloggers
Software or hardware. The attacker installs them on the victim's device and captures the  keys being pressed. 
### How to bypass simple keylogger
1. Copy pasting
2. Typing random letters with the real password in between then deleted the random characters
3. Reordering the characters by deleting and copy pasting
# Cryptography 
## Definition of terms
**Plaintext** 
- text can be read and understood
**Ciphertext** 
- unreadable texts
**Encryption**
- process of turning plaintext to ciphertext
**Decryption**
- process of turning ciphertext to plaintext 
**Cryptography**
- the encryption and decryption
**Cryptology**
- study of encryption and decryption
**Key**
- secret value used in decryption and encryption
- Public key and private key
## Types of Cryptographic algorithm
| Symmetrical                                           | Asymmetrical                                         | 
| ----------------------------------------------------- | ---------------------------------------------------- | 
| The key used in encryption and decryption is the same | Different keys are used in decryption and encryption |
| Caeser cipher                                         | RSA encryption algorithm                             | 
| How should the key be transferred?                    | It is safer as two keys would be needed to crack into the information                                           |
## Types of symmetrical cryptography
| Stream cipher                                                                    | Block cipher                                    |
| -------------------------------------------------------------------------------- | ----------------------------------------------- |
| Encrypts or decrypts one bit at a time                                           | Encrypts or decrypts a number of bits at a time |
|  Caeser Cipher | Transposition cipher                            |

## Cryptography Basis/Primitives
| Substitution                                                                                      | Transposition                                       |
| ------------------------------------------------------------------------------------------------- | --------------------------------------------------- |
| Replaces bits of data with another. If it involves letters, one letter is replaced one at a time. | Involves shifting the position of the letters/bits. |
| Changes the identity of the text without changing the position of the letters                                                                | Does not change the identity of the text.           |
| Caeser cipher                                                                                     | Columnar Transposition Cipher                       |
| Has recurring pattern that can be easily found out                                                |                                                     |

| Confusion                                                                                                                       | Diffusion                                                                             |
| ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| An encryption algorithm should not produce a ciphertext of which an attacker can easily identify the meaning of at first glance | The information should be spread throughout the entire cipher text                    |
| The attacker should not be able to predict what will happen if they change one letter                                           | The attacker would have to obtain much of the cipher text to understand the algorithm |
| Substitution creates confusion                                                                                                  | Transposition creates diffusion                                                       | 

## Cryptography techniques
### Caesar Cipher
- [i] Substitution cipher
- [?] How does it work?
	1. This cipher relies on the alphabet
	2. The person chooses a key to rearrange the alphabet
		1. If the key is 3, the alphabet shifts 3 to the right (encryption) and shifts 3 to the left (decryption)
#### Example
**Encryption**
M = Cyber security
Key = 3
A B C D E F G H I  J   K  L M N O  P  Q  R  S  T  U  V W  X  Y Z
D E F G H I  J  K L M N O  P Q  R  S  T   U V  W X  Y  Z  A  B C
C = FBEHU VHDXULWB
**Decryption**
D E F G H I  J  K L M N O  P Q  R  S  T   U V  W X  Y  Z  A  B C
A B C D E F G H I  J   K  L M N O  P  Q  R  S  T  U  V W  X  Y Z
M = Cyber security
### Columnar Transposition Cipher
- [i] Transposition cipher
- [?] How does it work?
	1. The cipher relies on rearranging the plaintext itself with a keyword
	2. The plain text will not include the keyword 
	3. The plain text is read vertically
#### Example
**Encryption**
Keyword = German
M = DEFEND THE EAST WALL

| G   | E   | R   | M   | A   | N   |
| --- | --- | --- | --- | --- | --- |
| D   | E   | F   | E   | N   | D   |
| T   | H   | E   | E   | A   | S   |
| T   | W   | A   | L   | L   | X    |

| A   | E   | G   | M   | N   | R   |
| --- | --- | --- | --- | --- | --- |
| N   | E   | D   | E   | D   | F    |
| A   | H   | T   | E   | S   |  E   |
| L   | W   | T   | L   | X   |   A  |

P = NALEHWDTTEELDSXFEA
### Monoalphabetic Ciphers
- [i] Each letter only appears one
#### Keyword Cipher
- [?] How does it work?
	1. Write the keyword down followed by the alphabet. 
	2. Make sure each letter only appear once
##### Example
Keyword = Wireless
Plaintext = Students
Ciphertext = VKOF

| W   | I   | R   | E   | L   | S   | A   | B   | C   | D   | F   | G   | H   | J   | K   | M   | N   | O   | P   | Q   | T   | U   | V   | X   | Y   | Z   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | 
| A   | B   | C   | D   | E   | F   | G   | H   | I   | J   | K   | L   | M   | N   | O   | P   | Q   | R   | S   | T   | U   | V   | W   | X   | Y   | Z   | 

C = PQTEJQP
M = WORK
#### Keyword mixed Cipher
- [?] How does it work?
	1. Write the keyword down. 
	2. Write the alphabets in the next row
	3. Read the new list of letters vertically
##### example
Keyword = WIRELESS
Plaintext = Team
Ciphertext = SEUR

| W   | I   | R   | E   | L   | S   |
| --- | --- | --- | --- | --- | --- |
| A   | B   | C   | D   | F   | G   |
| H   | J   | K   | M   | N   | O   |
| P   | Q   | T   | U   | V   | X   |
| Y   | Z    |     |     |     |     |

| W   | A   | H   | P   | Y   | I   | B   | J   | Q   | Z   | R   | C   | K   | T   | E   | D   | M   | U   | L   | F   | N   | V   | S   | G   | O   | X   |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| A   | B   | C   | D   | E   | F   | G   | H   | I   | J   | K   | L   | M   | N   | O   | P   | Q   | R   | S   | T   | U   | V   | W   | X   | Y   | Z    |

C = FYWK
M = WORK

#### Keyword Transposed Cipher
- [?] How does it work? 
	1. Write the keyword down. 
	2. Write the alphabets in the next row
	3. Rearrange the columns according to the keyword in alphabetical order
	5. Read the new list of letters vertically 
##### example

| W   | I   | R   | E   | L   | S   |
| --- | --- | --- | --- | --- | --- |
| A   | B   | C   | D   | F   | G   |
| H   | J   | K   | M   | N   | O   |
| P   | Q   | T   | U   | V   | X   |
| Y   | Z   |     |     |     |     |
|     |     |     |     |     |     |

| E   | I   | L   | R   | S   | W   |
| --- | --- | --- | --- | --- | --- |
| M   | B   | F   | C   | G   | A   |
| U   | J   | N   | K   | O   | H   | 
|     | Q   | V   | T   | X   | P   |
|     | Z   |     |     |     |  Y   |
#### Keyword Interrupted Cipher
- [?] How does it work? 
	1. Write the keyword down. 
	2. Replace the repeated letters with dos
	3. Write the alphabets in the next row
	4. Rearrange the columns according to the keyword in alphabetical order
	5. Read the new list of letters vertically 
##### example

| W   | I   | R   | E   | L   | $\cdot$ | S   | $\cdot$ |
| --- | --- | --- | --- | --- | ------- | --- | ------- |
| A   | B   | C   | D   | F   | G       | H   | J       |
| K   | M   | N   | O   | P   | Q       | T   | U       |
| V   | X   | Y   | Z   |    |         |   |         |


# Algorithms
**DES** - *Data Encryption Standard*
**RSA** 
**AES** - *Advance Encryption Standard*
## RSA encryption
### Formulas
**Encryption**
$$C = M^e \; mod\;N$$
**Decryption**
$$M = C^d \; mod \; N$$
- [?] How does it work? 
	1. Determine p and q first.
		1. Both are prime numbers
	2. Determine the n 
		1. n = p*q
	3. Determine the z
		1. z = (p-1)(q-1)
	4. Determine the e
		1. The e must be co-prime of z and is more than 1
**Public key combination**
(e, n)
**Private key combination**
(d, n)
**Formula**
$ed \;mod\;z  =1$
$ed = kz+1$

***Use Extended Euclidean Algorithm if the value is too large to compute***
# Private Key Protection
## How to protect private key
1. Transfer the key securely
2. Store the key securely
3. Determine the lifespan of the key based on the frequency of its usage and the importance of the information
4. Destroys the key and all of its traces once its lifespan is over
5. Should be changed frequency and does not use the previous values
6. Do not share it with anyone outside of the communication
# Message Digests
## Hash function
A program/algorithm that takes a variable length data and produces a fixed length output (hash value) no matter how large the input data is
This will prevent an interceptor from knowing how large or small the information is.
**Hash Message Authentication Code**
Both the input data and the secret code is put through the hash function, producing HMAC or simply, digital signature.
**Example**
1. MD
	1. MD4
	2. MD5
2. SHA
3. SHS
## Salt
Salt is a sequence of random numbers added to the password. This will prevent attackers from attempting rainbow table attacks, dictionary attacks, and list of password hashes. 

The salt is concatenated to the password before being put through the hash function. 
# Authentication technologies
## Determination of Identity Factors
1. Ownership factor
	1. smart card
2. Knowledge factor
	1. Question
3. Inherence factor
	1. Thumb-print
	2. DNA
## Authentication methods
### QR codes
- [i] Invented by the Japanese
- Uses Kanji, numeric, alphanumeric and byte/binary as encoding modes
### Barcodes
#### First generation
Use vertical lines -> one dimensional encoding scheme
#### Second generation
Uses symbols, squares -> two dimensional encoding scheme
Can be read by specialised optical scanners
### Magnetic strip card
Just a piece of plastic with magnetic strip on them. 
Has two tracks:
- The first track may have information such as full name, account number etc
- The second track may have information such account number and expiration date
#### The issue:
Anyone can easily buy a magnetic strip reader and writer online. This means anyone can read anybody's card and is also able to change the content in the card. 
### Smart cards
Cards with integrated circuit - microprocessor - with both ready and writing capabilities. 
### Sim cards
Common in mobile devices. Used to authenticate a device with the cellular network of the provider.
### Radio Frequency Identification, RFID
Uses part of the radio wave spectrum to transfer information. 
RFID tags are functional from a few cm to a few metres. 
Since it transmits information via radio-waves, the tag does not have to be inline with the scanner. 
#### Usage
This is also used with passports where the RFID chip contains digital facial photograph of the owner of the password which allows the officials to compare with the face of the holder. The RFID communication is also encrypted with a secret key which is passport number, date of birth and expiration date, in that order.
### Biometrics
#### Characteristics
1. Permanence
	1. It does not change for a long time unless something happens
2. Distinction
	1. Differentiate a person from another
3. Universality
	1. Everyone has it
4. Collectability
	1. Easy to collect
# Digital signatures
The most common digital signatures is the public key encryption. The signer computes a value using the private key. The receiver then uses the public key to verify that the signature actually came from the private key. [[Chapter 1 - Information Security Basics#RSA encryption| See also: RSA]]
## Characteristics 
1. Unforgeable
	1. Only the signer can produce the digital signature without the keys
2. Authentication
	1. The receiver can use the public key to verify the digital signature really came from the signer
3. Un-reusable
	1. Any attempt to reuse the digital signature can be easily found out by the receiver
4. Un-alterable
	1. The digital signature cannot be changed without being evident
## DSA
1. Not used for encryption but for producing digital signature. 
2. Two keys are used in DSA
	1. The first key comes from the hash function/algorithm
	2. The second key comes from the private key
3. A message digest is generated from the hash function
4. The message digest is then encrypted using the private key
## RSA Digital signature process
1. The data is put through a hash function 
2. The hash value is then encrypted with a private key, producing the digital signature
3. The digital signature is then sent together with the data
4. The data on the receiver end will put it through the hashing algorithm
5. The digital signature will be decrypted with the public key
6. If the hash values are the same, integrity has been preserved

# Chapter 2
[[Chapter 2 - OS Security & Malware Analysis]]