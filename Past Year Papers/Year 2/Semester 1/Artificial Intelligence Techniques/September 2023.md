---
aliases:
  - September 2023
tags:
  - PYQ
  - Artificial-Intelligence-Technique
Creation Date: 2024-08-12T19:25:00
Completion: true
obsidianUIMode: preview
---
# Section A
## Question 1
### Question A
1. $P(W_s) = 0.15+0.2+0.05+0.15 = 0.55$
2. $P(W_s, T_c) = 0.15 + 0.05 = 0.2$
$$
\begin{align} 
P(R|W_s, T_c) &= \frac{P(R, W_s, T_c)}{P(W_s, T_c)} \\ 
& = \frac{0.15}{0.2} \\
& = 0.75
\end{align}
$$
$$
\begin{align}
P(R|W_s) &= \frac{P(R,W_s)}{P(W_s)} \\
&= \frac{0.15 + 0.2}{0.55} \\
& = 0.64
\end{align}
$$
### Question B
#### Question I
B and C are dependent on A
D is dependent on B and C but independent of A
#### Question II
$$
\begin{align}
P(\neg a, \neg b, \neg c, \neg d) &= P(\neg a) P(\neg b|\neg a)P(\neg c| \neg a) P(\neg d | \neg b, \neg c)\\
& =0.7 \times 0.8 \times 0.6 \times0.9 \\
& = 0.3024
\end{align}
$$
#### Question III
$$
\begin{align}
P(b,c,d) &= \sum_{a} P(d|b,c) \\
& = \sum P(a) P(b|a)P(c|a) P(d|b,c) \\
& = P(a) \sum P(b|a)P(c|a) P(d|b,c) \\
\end{align}
$$
Both $\neg a$ and $a$ has to be considered in calculation
$P(a) = 0.3$ and $P(\neg a) = 0.7$
$$
\begin{align}
P(b|a) &= 0.8 \qquad P(c|a) &= 0.6\\ 
P(b|\neg a) &= 0.2 \qquad P(c|\neg a) &= 0.4\\
\end{align}
$$
$$
\begin{align}
P(b,c,d) &= \sum_{a} P(d|b,c) \\
& = \sum P(a) P(b|a)P(c|a) P(d|b,c) \\
& = \sum P(a) P(b|a)P(c|a) P(d|b,c) \\
& = (0.3 \cdot 0.8 \cdot 0.6 \cdot 0.9)  \; + \; (0.7 \cdot 0.2 \cdot 0.4 \cdot 0.9) \\
& = 0.1296 + 0.0504 \\
& = 0.18 \\
\therefore P(b,c,d) &= 0.18
\end{align}
$$
#### Question IV
$$
\begin{align}
P(b,c|a) &= P(b|a) P(c|a) \\
& = 0.8 \cdot 0.6 \\
& = 0.48
\end{align}
$$
#### Question V
D is independent of A
$$
\begin{align}
P(d|a,\neg b, c) &= P(d|\neg b, c) \\
& = 0.6 \\
\end{align}
$$
## Question 2
### Question A
![[Past Year Papers/Year 2/Semester 1/Artificial Intelligence Techniques/Diagrams/september_2023/ucs|700]]
### Question B
#### Question I
![[a_star_search|700]]
yes, the predicted cost is lower than the actual cost in each node
A* Search is more efficient than UCS because it uses a heuristic function, making it forward looking than only relying short term rewards. With a heuristic function, the algorithm can know if the node is closer or farther from the goal, reducing the expansion of unnecessary nodes. However, in UCS, nodes are expanded blindly because it does not consider cost beyond the immediate cumulative path cost
### Question C
No. The solution found is the least optimal when compared to using A* search or UCS. Both A* search and UCS manages to find the optimal solution but, DFS tree does not. The cost after finding the path is 7.

There exists a loop between node A and Node B. If nodes are expanded with alphabetical order, this means that node A and Node B will be expanded infinitely. The solution will not be found. 
## Question 3
### Question A

| Actual | Predicted | TN  | TP  | FN  | FP  |
| ------ | --------- | --- | --- | --- | --- |
| 1      | 1         |     | 1   |     |     |
| 0      | 1         |     |     |     | 1   |
| 1      | 0         |     |     | 1   |     |
| 1      | 1         |     | 1   |     |     |
| 1      | 1         |     | 1   |     |     |
| 1      | 0         |     |     | 1   |     |
| 0      | 0         | 1   |     |     |     |
| 0      | 0         | 1   |     |     |     |
| 1      | 1         |     | 1   |     |     |
| 1      | 1         |     | 1   |     |     |
| Sum    | <         | 2   | 5   | 2   | 1   |

|   TN = 2   |   FP = 1   |
| :--------: | :--------: |
| **FN** = 2 | **TP** = 5 |
$$
\begin{align}
\text{Accuracy} &= \frac{7}{10} \\
\text{Precision} &= \frac{5}{6} \\
\text{Recall} &= \frac{5}{7} \\
\text{F}_1 \text{ score} &= \frac{10}{13} \\
\end{align}
$$
### Question B
Decrease the threshold value of the classifier. This means that the amount of False Negatives will be reduced.
### Question C
![[mdp_representation|700]]
The *State, S* represents the set of the current situations that the Agent is in. In the algorithm there exists a start state, and a terminal state/goal state. The *Action, A* represents the set of all the possible actions that can be taken by the agent in a given state in the environment. When the agent performs an action, the environment returns the new state after the action and the reward, which can be positive or negative, to the agent. The agent then adds the action to its policy.   
### Question D
$$Q(s,a) = Q(s,a) + \alpha(\;R(s,a) + \gamma \max Q(s',a') - Q(s,a)\;)$$

|     | left | right |
| :-: | :--: | :---: |
|  1  |  0   |   0   |
|  2  |  0   |   0   |
|  3  |  0   |   0   |
|  4  |  0   |   0   |
|  5  |  0   |   0   |
$\alpha = 0.5$, $\gamma = 0.9$
#### First Episode
$$Q(2,R) = 0 + 0.5\cdot(\;0 +  0.9\cdot 0 - 0\;) = 0$$
$$Q(3,L) = 0 + 0.5\cdot(\;0 +  0.9\cdot 0 - 0\;) = 0$$
$$Q(2,R) = 0 + 0.5\cdot(\;0 +  0.9\cdot 0 - 0\;) = 0$$
$$Q(3,R) = 0 + 0.5\cdot(\;0 +  0.9\cdot 0 - 0\;) = 0$$
$$Q(4,R) = 0 + 0.5\cdot(\;2 +  0.9\cdot 0 - 0\;) = 1$$

|     | left | right |
| :-: | :--: | :---: |
|  1  |  0   |   0   |
|  2  |  0   |   0   |
|  3  |  0   |   0   |
|  4  |  0   |   1   |
|  5  |  0   |   0   |
#### Second Episode
$$Q(2,R) = 0 + 0.5\cdot(\;0 +  0.9\cdot 0 - 0\;) = 0$$
$$Q(3,R) = 0 + 0.5\cdot(\;0 +  0.9\cdot 1 - 0\;) = 0.45 $$
$$Q(4,R) = 1 + 0.5\cdot(\;2 +  0.9\cdot 0 - 1\;) = 1.5 $$

|     | left | right |
| --- | ---- | ----- |
| 1   | 0    | 0     |
| 2   | 0    | 0     |
| 3   | 0    | 0.45  |
| 4   | 0    | 1.5   |
| 5   | 0    | 0     |
# Section B
## Question 4

### Question A

|     Models      |           Discriminative Models            |                  Generative Models                  |
| :-------------: | :----------------------------------------: | :-------------------------------------------------: |
| **Differences** |    Focuses on finding decision boundary    |    Calculates probabilistic model for each class    |
|        ^        |     Decision is made based on distance     |        Decision is made based on probability        |
|        ^        | Focuses on predicting labels of the output |           Capable of creating new sample            |
|        ^        |                                            | Focus on explaining how the new samples are created |

### Question B
| x   | y   |
| --- | --- |
| 2   | 25  |
| 4   | 45  |
| 6   | 55  |
| 9   | 55  |
| 11  | 45  |
^table
This is a regression task. The output is not a label or a category, it is a continuous value. 
*Single:* $h(x) = \theta^T X$ or $X^T \theta$ 
*Multiple:* $h(x) = X \cdot \theta$
$$\text{RMSE} = \sqrt{\frac{1}{m}\sum_{i=1}^m{(h_\theta(x^{(i)} - y^{(i)})^2}}$$$$\text{MSE} = \frac{1}{m}(X\cdot\theta - y)^{\mathrm{ T }}(X\cdot\theta - y)$$
$$\text{RMSE} = \sqrt{\frac{1}{m}(X\cdot\theta - y)^{\mathrm{ T }}(X\cdot\theta - y)}$$
$$(X\cdot\theta - y)$$
$$\begin{bmatrix}
1 & 2 \\
1 & 4 \\
1 & 6 \\
1 & 9 \\
1 & 11 \\
\end{bmatrix} 
\cdot 
\begin{bmatrix} 
30 \\ 2
\end{bmatrix}
- 
\begin{bmatrix}
25\\
45\\
55\\
55\\
45\\
\end{bmatrix}
= 
\begin{bmatrix}
34 \\
38 \\
42 \\
48 \\
52 \\
\end{bmatrix} 
-
\begin{bmatrix}
25\\
45\\
55\\
55\\
45\\
\end{bmatrix}
= 
\begin{bmatrix}
9\\
-7\\
-13\\
-7\\
7\\
\end{bmatrix}
$$
$$
\begin{bmatrix}
9\\
-7\\
-13\\
-7\\
7\\
\end{bmatrix} ^{\mathrm{T}} 
\cdot 
\begin{bmatrix}
9\\
-7\\
-13\\
-7\\
7\\
\end{bmatrix}
= 
\begin{bmatrix}
9 & -7 & -13 & -7 & 7  
\end{bmatrix} \cdot
\begin{bmatrix}
9\\
-7\\
-13\\
-7\\
7\\
\end{bmatrix}
= 397
$$
$$\text{RMSE} = \sqrt{\frac{1}{5}\times 396.95}$$
$$\text{RMSE} = 8.91$$

The linear model is just right for the data. This is because there is only one feature to consider and the number of samples is small, with only 5 samples of data.
##### Polynomial model
$$\text{RMSE} = \sqrt{\frac{1}{m}(X\cdot\theta - y)^{\mathrm{ T }}(X\cdot\theta - y)}$$
$$X\cdot\theta$$
$$
\begin{bmatrix}
1 & 2 & 4\\
1 & 4 & 16\\
1 & 6 & 36\\
1 & 9 & 81\\
1 & 11 & 121 
\end{bmatrix}
\cdot
\begin{bmatrix} 
-2 \\ 
16 \\
-1.06
\end{bmatrix}
= 
\begin{bmatrix}
25.76 \\
45.04 \\
55.84 \\
56.14 \\
45.74 
\end{bmatrix}
$$
$$(X\cdot\theta -y)$$
$$
\begin{bmatrix}
 25.76 \\
 45.04 \\
 55.84 \\
 56.14 \\
 45.74 
\end{bmatrix}
-
\begin{bmatrix}
 25 \\
 45 \\
 55 \\
 55  \\
 45 
\end{bmatrix}
=
\begin{bmatrix}
 0.76 \\
 0.04 \\
 0.84 \\
 1.14  \\
 0.74 
\end{bmatrix}
$$


$$(X\cdot\theta -y)^T \cdot (X\cdot\theta -y)$$
$$
\begin{bmatrix}
 0.76 &
 0.04 &
 0.84 &
 1.14 &
 0.74 
\end{bmatrix}
\cdot
\begin{bmatrix}
 0.76 \\
 0.04 \\
 0.84 \\
 1.14  \\
 0.74 
\end{bmatrix}
 =
 3.132
$$
$$\frac{1}{m} \times (X\cdot\theta -y)^T \cdot (X\cdot\theta -y)$$
$$\frac{1}{5} \times 3.132 = 0.6264$$
$$\sqrt{0.62664} = 0.7915$$
Feature scaling. 
Dimensionality reduction. Select features that are important or reduce the number of features

Regularisation can be applied on the model
*Ridge regression* and *Lasso regression*
In ridge regularisation, the model is set to prefer parameters with smaller values rather than bigger ones. 
Lasso regularisation tends to generate solution that is sparse and eliminate the weights of the least important features

## Question 5
### Question A
#### Question I
$$\sigma{(\theta^T X)} = \frac{1}{1 + e ^{-(\theta_0 + \theta_1x_1)}}$$
#### Question II
Single sample: $$\sigma{(\theta^T X)} = \frac{1}{1 + e ^{-\theta^T X}}$$
Multiple sample: $$\sigma{(\theta^T X)} = \frac{1}{1 + e ^{X \cdot\theta}}$$
**Model A**
$$
\begin{bmatrix}
1 & 3 \\
1 & 5 \\
1 & 7 \\
1 & 9 \\
\end{bmatrix}
\cdot
\begin{bmatrix} 
-3 \\ 
0.5 \\
\end{bmatrix}
 = 
\begin{bmatrix}
-1.5 \\
-0.5 \\
0.5 \\
1.5 \\
\end{bmatrix}
$$

|  X  | $h_\theta(x)$ |   $\hat p$   | real | predicted |
| :-: | :-----------: | :----------: | :--: | :-------: |
|  3  |    0.1824     | 0.1824 < 0.5 |  no  |    no     |
|  5  |    0.3775     | 0.3775 < 0.5 |  no  |    no     |
|  7  |    0.6225     | 0.6225 > 0.5 | yes  |    yes    |
|  9  |    0.8176     | 0.8176 > 0.5 | yes  |    yes    |
Accuracy = 4/4

**Model B**

$$
\begin{bmatrix}
1 & 3 \\
1 & 5 \\
1 & 7 \\
1 & 9 \\
\end{bmatrix}
\cdot
\begin{bmatrix} 
-1 \\ 
0.3 \\
\end{bmatrix}
 = 
\begin{bmatrix}
-0.1 \\
0.5 \\
1.1 \\
1.7 \\
\end{bmatrix}
$$

|  X  | $h_\theta(x)$ |   $\hat p$   | real | predicted |
| :-: | :-----------: | :----------: | :--: | :-------: |
|  3  |    0.4750     | 0.4750 < 0.5 |  no  |    no     |
|  5  |    0.6225     | 0.6225 > 0.5 |  no  |    yes    |
|  7  |    0.7503     | 0.7503 > 0.5 | yes  |    yes    |
|  9  |    0.8455     | 0.8455 > 0.5 | yes  |    yes    |
Accuracy = 3/4
Model A fits better
### Question B
#### Question I
$$f'(x_1) = 6x_1 + 2x_2$$
$$f'(x_2) = 2x_1 + 2x_2$$

$$x_1' := x_1 - \eta ( 6x_1 + 2x_2)$$
$$x_2' := x_2 - \eta ( 2x_1 + 2x_2)$$
#### Question II

| $x_1$ | $x_2$ | $f'(x_1)$ | $f'(x_2)$ | $x_1'$ | $x_2'$ | $f(x_1, x_2)$ |
| :---: | :---: | :-------: | :-------: | :----: | :----: | :-----------: |
|   1   |   1   |     8     |     4     |  0.2   |  0.6   |     3.72      |
|  0.2  |  0.6  |    2.4    |    1.6    | -0.04  |  0.44  |     3.16      |

#### Question III
Yes, the $f(x_1,x_2)$ is decreasing in each new iteration. 
# See Next
[[Past Year Papers/Year 2/Semester 1/Artificial Intelligence Techniques/December 2022|December 2022]]