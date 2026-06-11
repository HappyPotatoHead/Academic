---
aliases:
  - Logic Gates
tags:
  - Notes
  - ICOA
Date: 2023-09-18
Completion: true
obsidianUIMode: preview
---
# Data transfer
Serial Data Transfer
- 1 bit is transferred one cycle at a time
Parallel Data Transfer
- A group of bits are transferred in one cycle
# Basic Logic Gate
**Assumes you already know each logic gates**
**NAND** & **NOR** gate is the most fundamental gate of all
## NAND GATE
Can form **NOT**, **AND**, **OR** GATES
![[nand_gate]]

## NOR GATE
Can form **NOT**, **OR**, **AND** gates
![[nor_gate]]

# Boolean Algebra
>[!IMPORTANT] FORMULAS
> $$A+A = A$$ $$A\cdot A = A$$
> $$A+1 = 1$$ $$A\cdot1 = A$$
> $$A+0 = A$$ $$A\cdot0 = 0$$
> $$A + \bar A = 0$$ $$A\cdot A = 0$$
> $$\bar{\bar A} = A$$
> $$A + AB = A$$ $$A+\bar AB = A + B$$
> $$(A+B)(A+C) = A + BC$$
>  

## Redundancy Rule
$$xy + \bar x z + yz$$
BECOMES
$$xy+\bar xz$$
## DeMorgan's Theoram
$$\overline{(A+B)} = \bar A \cdot \bar B$$
$$\overline{(A\cdot B)} = \bar A + \bar B $$

# SOP AND POS
## SOP -> Sum of Product
Finds minterm(1)/ output is 1
Overhead bar cannot extend beyond one variable
$$A(B+CD)$$
$$AB + CD$$
$$AB(\bar C + C)(\bar D + D) + CD(\bar A+ A)(\bar B + B)$$**Expand and simplify**
## POS -> Product of Sum
Finds maxterm(0)/ output is 0
Overhead bar cannot extend beyond one variable
$$(A+\bar B)(B+C)$$
$$(A+\bar B + \bar CC)(B+C+\bar AA)$$
$$(A+\bar B + \bar C)(A + \bar B + C)(\bar A + C + C)(A +B +C)$$
# Combinational circuit building blocks
## Decoder
The most common decoder is the binary decoder. 
### Binary Decoder
n to $2^n$ decoders
**Example**
2 to 4 binary decoder
Binary decoder has multiple inputs and multiple outputs. However, the combination of the inputs will choose one from the outputs.

**Example - Normal Decoder**

| INPUTS |      |      | OUTPUT |      |      |      |
| ------ | ---- | ---- | ------ | ---- | ---- | ---- |
| en     | a[1] | a[2] | y[3]   | y[2] | y[1] | y[0] |
| 0      | d    | d    | 0      | 0    | 0    | 0    |
| 1      | 0    | 0    | 0      | 0    | 0    | 1    |
| 1      | 0    | 1    | 0      | 0     | 1    | 0     |
| 1      | 1    | 0    | 0      | 1    |   0   |   0   |
| 1      | 1    | 1    | 1      |  0    |   0   |     0 |

**Example - Inverted Decoder**

| INPUTS |      |      | OUTPUT |      |      |      |
| ------ | ---- | ---- | ------ | ---- | ---- | ---- |
| en     | a[1] | a[2] | y[3]   | y[2] | y[1] | y[0] |
| 0      | d    | d    | 0      | 0    | 0    | 0    |
| 1      | 0    | 0    | 1      | 1    | 1    | 0    |
| 1      | 0    | 1    | 1      | 1    | 0    | 1    |
| 1      | 1    | 0    | 1      | 0    | 1    | 1    |
| 1      | 1    | 1    | 0      | 1    | 1    | 1    |

### Display Decoder
Just another form of decoder

## Multiplexer
There is data inputs and one output. There will be selectors that choose the data inputs.
$2^n$ - the 'n' is the number of selectors

**Example - 4 to 1 multiplexer/$2^2$ to 1**

![[decoder_and_multiplexer]]
### Multiplexer expansion
A few multiplexer can be combined to form one bigger multiplexer

## Adder 
### Half adder 
Sum = $A\oplus B$
Cout = $A\cdot B$
### Full adder
Sum = $A\oplus B \oplus cin$
Cout = $A \oplus B \cdot cin + A \cdot B$

# Arithmetic 
## Overflowing
The result is out of range, over-flow will occur
For unsigned arithmetic, the carry out indicates overflow
For signed arithmetic, the carry out is not enough to indicate overflow

# Delay Flip Flops/ Clock timer
Areset - makes the output into 0 immediately until the next clock cycle
Aset - makes the output into 1 immediately until the next clock cycle

A positive clock timer will copy the preceding input as the next output according to the positive edge.
A negative clock timer will copy the preceding input as the next output according to the negative edge.

## Register Files
Register files are just collection of a group of registers. 
# Chapter 4 - Programming
[[Chapter 4 - MIPS Assembly Language]]