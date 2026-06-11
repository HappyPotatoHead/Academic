---
aliases:
  - December 2023
tags:
  - PYQ
  - Discrete-Maths
Creation Date: 2024-05-22T13:42:00
Completion: true
obsidianUIMode: preview
---
# Section A
## Question 1
### Question A
- Let p = Jason buys the book
- Let q = Jason goes to the shop
$p \Rightarrow q$
**Negation**
$$\begin{align}
\thicksim (p \Rightarrow q)\\
p \; \land \thicksim \; q
\end{align}$$
Jason buys the book and Jason does not go to the shop
**Converse**
$$\begin{align}
p \Rightarrow q \\
q \Rightarrow  p \\
\end{align}$$
If Jason goes to the shop, then Jason buys the book
**Inverse**
$$\begin{align}
p \Rightarrow q \\
\thicksim p \Rightarrow \; \thicksim q \\
\end{align}$$
If Jason does not buy the book, then Jason does not go to the shop
**Contrapositive**
$$\begin{align}
p \Rightarrow q \\
\thicksim q \Rightarrow \; \thicksim p \\
\end{align}$$
If Jason does not go to the shop, then Jason does not buy the book
### Question B
- Let p = Sara is a math major
- Let q = Sara is an economics major
- Let r = Sara is required to take Calculus
$$\begin{align}
p \lor q \\
q \Rightarrow r \\
\therefore \; q \; \lor \thicksim r
\end{align}$$

| p   | q   | r   | $\thicksim$r | $p \lor q$ | q$\Rightarrow$r | $p \lor q$ $\land$ q$\Rightarrow$r | $q \; \lor \thicksim r$ | $\Rightarrow$ |
| --- | --- | --- | ------------ | ---------- | --------------- | ---------------------------------- | ----------------------- | ------------- |
| F   | F   | F   | T            | F          | T               | F                                  | T                       | T             |
| F   | F   | T   | F            | F          | T               | F                                  | F                       | T             |
| F   | T   | F   | T            | T          | F               | F                                  | T                       | T             |
| F   | T   | T   | F            | T          | T               | T                                  | T                       | T             |
| T   | F   | F   | T            | T          | T               | T                                  | T                       | T             |
| T   | F   | T   | F            | T          | T               | T                                  | F                       | F             |
| T   | T   | F   | T            | T          | F               | F                                  | T                       | T             |
| T   | T   | T   | F            | T          | T               | T                                  | T                       | T             |
The statement is invalid. *Use shortcut method to check*
### Question C
#### Question I
False. When both x and y = 1
$$\sqrt{1+1} \neq \sqrt{1} + \sqrt{1}$$
#### Question II
**Formal**
$\exists x,\forall y \in R$, $\sqrt{1+1} \neq \sqrt{1} + \sqrt{1}$
**Informal**
There exist a real number x such that all every number y, the $\sqrt{1+1} \neq \sqrt{1} + \sqrt{1}$
## Question 2
### Question A
$$\frac{n(-1)^{n+1}}{(n+1)^2}$$
### Question B
![[Past Year Papers/Year 1/Semester 3/Discrete Maths/Diagrams/december_2023/mathematical_induction|mathematical_induction]]
### Question C
#### Question I
*Pretty self explanatory*
#### Question II
![[fibonnaci]]
## Question 3
### Question A
#### Question I
\[1\] = \[2\] = \[3\] = \[5\] = {1,2,3,5}
\[4\] = {4} 
A/R = \{\[1\],\[4\]\}
#### Question II
1. It is reflexive
	- (a,a) $\in$ R $\forall a \in A$ 
2. It is not irreflexive
	- $\forall$(a,a) $\in$ R
	- It is already reflexive
3. It is symmetric
	- (a,b) $\in$ R and (b,a) $\in$ R
4. It is not antisymmetric
5. It is not asymmetric
6. It is transitive
	- $M_{R^2} = M_R$
### Question B
#### Question I
![[Past Year Papers/Year 1/Semester 3/Discrete Maths/Diagrams/december_2023/hasse]]
#### Question II
Maximal = 288, 432
Minimal = 4
#### Question III
Greatest = none
Least = 4
# Section B
## Question 4
### Question A
![[Past Year Papers/Year 1/Semester 3/Discrete Maths/Diagrams/december_2023/algebraic_tree|algebraic_tree]]
### Question B
1. Preorder
	- Visit the root, $v$
	- If $v_L$ exists, apply the algorithm to the left subtree $(T(v_L), v_L)$
	- If $v_R$ exists, apply the algorithm to the right subtree $(T(v_R), v_R)$
2. Inorder
	- If $v_L$ exists, apply the algorithm to the left subtree $(T(v_L), v_L)$
	- Visit the root, $v$
	- If $v_R$ exists, apply the algorithm to the right subtree $(T(v_R), v_R)$
4. Postorder
	- If $v_L$ exists, apply the algorithm to the left subtree $(T(v_L), v_L)$
	- If $v_R$ exists, apply the algorithm to the right subtree $(T(v_R), v_R)$
	- Visit the root, $v$
### Question C
**Preorder**
a b d e h k c f i l g j
**Inorder**
d b h k e a f l i c j g
**Postorder**
d k h e b l i f j g c a