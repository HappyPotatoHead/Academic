---
aliases:
  - Number Systems
tags:
  - Notes
  - ICOA
Date: 2023-09-19
Completion: true
obsidianUIMode: preview
---
# Part 1 - Introduction
1. Decimal 
	- 0 - 9 
1. Binary
	- 0 and 1
1. Octal
	- 0 - 7
	- Represented by 3 binary bits
1. Hexadecimal
	- 0 -9, A - F
	- Represented by 4 binary bits
	- 2 hexadecimals is one byte
## Conversion of Number Bases
**Base 10** to any other **bases**-> division
**Any other bases** to **Base 10** -> multiplication
**Any bases** to **any bases** -> convert to binary first
If the numbers have decimal points
**Example**
$1F.C_{16}$ 
$1(16^1) + 15(16^0) + 12(16^{-2}) = 31.75_{10}$ 
$31/10 = 0001 1111_{2}$
$0.75 \times 2 = 1.5\qquad 1$
$0.5\times2= 1 \qquad\quad\;1$
**Result:: ** $00001 \; 1111.1100$
**or**
Convert into binary
$0001 \;1111. 1100_2$

# Part 2 - Gray Code & BCD
## Binary Coded Decimals
A decimal number from 0 to 9 is represented with 4 binary digits
**Example**
$129_{10} = 0001\;0010\;1001_{BCD}$
$1000\;0110_{BCD} = 86_{10}$

## Gray codes
Gray codes are not weighted by anything. 
Reduce the error rate during data transfer - there is lesser bit change. Less likely for a bit to be wrong.
## Conversion
![[g_to_b_vice_versa]]
**More example**
**Binary to gray code**
$1010_{2} = 1111_{G}$
$0110_{2} = 0101_{G}$
$0011_{2} = 0010_{G}$
$1001_{2} = 1101_{G}$
**Gray code to binary**
*If same = 0, not same = 1*
$1010_{G} = 1100_{2}$
$0110_{G} = 0110_{2}$
$0011_{G} = 0010_{2}$
$1001_{G} = 1110_{2}$
# Part 3 - Negative & Arithmetic 
## Negative binary
Negative numbers  are represented by Signed Magnitude and 2's Complement
The first digit is represents positive or negative -> 0 is positive & 1 is negative
### Signed Magnitude
The first digit is the signed bit. The rest of the bits are the true magnitude. This is the same regardless if the values are positive or negative
### 2's Complement
The first digit is the signed bit. IF the number is positive, the 2's complement is true binary. 
IF the number is negative. 
1. Invert the 2's complement
2. +1 
3. Convert into decimal
4. Add a "-"
## Arithmetic 
$$A - B = A + (-B)$$
$$\qquad\;\;\;\;\;\;\;= A\;+1+B\;'$$

# Next Chapter 
[[Chapter 3 - Logic Gates|Logic Gates]]