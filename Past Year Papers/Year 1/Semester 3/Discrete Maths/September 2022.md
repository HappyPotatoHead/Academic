---
aliases:
  - September 2022
tags:
  - PYQ
  - Discrete-Maths
Creation Date: 2024-05-22T13:43:00
Completion: true
obsidianUIMode: preview
---
# Section A
## Question 1
### Question a
- Let p = the road goes to the capital
- Let q = the bus stop is here
$$\begin{align}
& p \Rightarrow \; \thicksim q \\
& q \Rightarrow \; \thicksim p \\
& \therefore \; p \lor q 
\end{align}$$

| p   | q   | ~p  | ~q  | p$\Rightarrow$~q | q$\Rightarrow$~p | p$\vee$q | (p$\Rightarrow$~q) $\land$ (q $\Rightarrow$~p) | $\Rightarrow$ |
| --- | --- | --- | --- | ---------------- | ---------------- | -------- | ---------------------------------------------- | ------------- |
| F   | F   | T   | T   | T                | T                | F        | T                                              | F             |
| F   | T   | T   | F   | T                | F                | T        | F                                              | T             |
| T   | F   | F   | T   | F                | T                | T        | F                                              | T             |
| T   | T   | F   | F   | T                | T                | T        | T                                              | T             |
### Question B
#### Question I
For every integer, there exist another integer such that the summation of both integers result in 0.
**True**. Every integer has its negative that will sum up to 0
#### Question II
There exists an integer such the summation of the integer with all other integers result in 0.
False. Each integer can only sum with its negative self to get a 0.
### Question C
![[Past Year Papers/Year 1/Semester 3/Discrete Maths/Diagrams/september_2022/without_truth_table|without_truth_table]]
## Question 2
### Question A
![[Past Year Papers/Year 1/Semester 3/Discrete Maths/Diagrams/september_2022/mathematical_induction|mathematical_induction]]
### Question B
![[Past Year Papers/Year 1/Semester 3/Discrete Maths/Diagrams/september_2022/recursion|recursion]]
### Question C
![[recursion_2]]
## Question 3
### Question A
$$\begin{align}
R(3) = \{0\}\\
R(4) = \{\} \\
R(5) = \{\} \\
R(6) = \{\} \\
\end{align}$$
$$\therefore R(\{3,4,5,6\}) = R(3) \cap
R(4) \cap
R(5) \cap
R(6) = \{0\}$$
### Question B 
Maximal = e
Minimal = h, i
Greatest = e
Least = none
### Question C
#### Question I
![[Past Year Papers/Year 1/Semester 3/Discrete Maths/Diagrams/september_2022/hasse]]
#### Question I
Every pair has Least Upper Bound and Greatest Lower Bound
### Question D
#### Question I
By using $a \; \lor \; (b \land c) \equiv \; (a\;\lor \; b)\land(a \; \lor \; c)$ .
The greatest and least element should not be chosen as the part of the group of 3 as the equation will always be true. 
#### Question II
By selecting two vertices that do not have a connection. The Least Upper Bound and Greatest Lower bound of the pair should be the least and greatest element.
# Section B
## Question 4
### Question A
#### Question I
![[prim_algorithm]]
$T = \{(A,D),(D,F),(D,B),(B,E),(E,G),(E,C),(C,I),(I,H)\}$
Weight = 42
#### Question II
*Too long so I list steps instead*
**Steps**
1. List down the weight and path in ascending order
2. Starting from the top, choose the paths
3. Check to see if there's a cycle
- [!] THE TOTAL WEIGHT MUST BE THE SAME
### Question C
1. Find the shortest path to the destination when driving
2. Electrical grid
3. Water supply path
4. Telecommunication network
## Question 5
### Question A
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
### Question B
**Pre order**
a b d e h k c f i l g j 
**In order**
d b h k e a f l i c j g
Post order
d k h e b l i f j g c a
### Question C
1. Efficient searching in computer algorithm
4. Indexing
5. Dictionary
6. Spelling checks