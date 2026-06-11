---
aliases:
  - December 2023
tags:
  - PYQ
  - Artificial-Intelligence-Technique
Creation Date: 2024-09-18
Finished Date: 2024-09-18
Completion: true
obsidianUIMode: preview
---
# Section A
## Question 1

### Question A
#### Question I
![[bfs|700]]
#### Question II
Path: $A \rightarrow B \rightarrow C \rightarrow F$
6+7+3 = 16
#### Question III
No. BFS only produces optimal paths if the cost of the path are increasing monotonically layer by layer.
There is a path with lesser cost which is $A \rightarrow D \rightarrow E \rightarrow F$
##### Question IV
\10. (since 10 nodes explored)
### Question B
#### Question I
![[Past Year Papers/Year 2/Semester 1/Artificial Intelligence Techniques/Diagrams/december_2023/ucs|700]]
#### Question II
$A \rightarrow D \rightarrow E \rightarrow F$. Cost = 10
#### Question III
Yes. Since UCS always explores the path with the cheapest cost
#### Question IV
6 since 6 nodes explored
## Question 2
### Question A

| Type of Learning/ Differences | -   |                                      Supervised                                      |                       Unsupervised                        |              Reinforced Learning              |
| ----------------------------- | --- | :----------------------------------------------------------------------------------: | :-------------------------------------------------------: | :-------------------------------------------: |
| 1                             | -   |                                 External supervision                                 |                      No supervision                       |                No supervision                 |
| 2                             | -   |                            The data given come with tags                             |             Data given do not come with tags              |               No data is given                |
| 3                             | -   | Solves model by creating a mathematical model that maps the input to the output data |       Solves problem by finding underlying patterns       |      Solves problem with trial and error      |
| 4                             | -   |                       Focuses on classification and regression                       | The algorithm focuses on clustering and association tasks | Focuses on assisting in decision making tasks |
### Question B
#### Question I
This is a regression tasks. The objective is to find the income which is a continuous number. (*You are trying to predict a continuous number*)
#### Question II
$h_{\theta}(x) = \theta_0 + \theta_1(x_1)$
#### Question III
*Model A*
$$
\begin{align}
MSE & = \frac{1}{m}(h_\theta(x) - y)^2 \\
& = \frac{1}{m}(X\cdot \theta - y)^2 \\
& = \frac{1}{4}( 
\begin{bmatrix}
1 & 1 \\
1 & 4 \\
1 & 7 \\
1 & 9 
\end{bmatrix}
\cdot 
\begin{bmatrix}
15 \\
6 
\end{bmatrix}
- 
\begin{bmatrix}
25 \\
32 \\
53 \\
75  
\end{bmatrix}
)^2 \\
& = \frac{1}{4}(
\begin{bmatrix}
21 \\
39 \\
57 \\
69 
\end{bmatrix}
- 
\begin{bmatrix}
25 \\
32 \\
53 \\
75  
\end{bmatrix}
)^2\\
& = \frac{1}{4}(
\begin{bmatrix}
-4 \\
7 \\
4 \\
-6 
\end{bmatrix}
)^2\\
& = \frac{1}{4}(
\begin{bmatrix}
-4 & 7 & 4 & -6\\
\end{bmatrix}
\begin{bmatrix}
-4 \\
7 \\
4 \\
-6 
\end{bmatrix}
)\\
& = \frac{1}{4}(117)\\
& = 29.25
\end{align}
$$

*Model B*
$$
\begin{align}
MSE & = \frac{1}{m}(h_\theta(x) - y)^2 \\
& = \frac{1}{m}(X\cdot \theta - y)^2 \\
& = \frac{1}{4}( 
\begin{bmatrix}
1 & 1 \\
1 & 4 \\
1 & 7 \\
1 & 9 
\end{bmatrix}
\cdot 
\begin{bmatrix}
30 \\
3
\end{bmatrix}
- 
\begin{bmatrix}
25 \\
32 \\
53 \\
75  
\end{bmatrix}
)^2 \\
& = \frac{1}{4}(
\begin{bmatrix}
33 \\
42 \\
51 \\
57 
\end{bmatrix}
- 
\begin{bmatrix}
25 \\
32 \\
53 \\
75  
\end{bmatrix}
)^2\\
& = \frac{1}{4}(
\begin{bmatrix}
8 \\
10 \\
-2 \\
-18 
\end{bmatrix}
)^2\\
& = \frac{1}{4}(
\begin{bmatrix}
8 & 10 & -2 & -18\\
\end{bmatrix}
\begin{bmatrix}
8 \\
10 \\
-2 \\
-18 
\end{bmatrix}
)\\
& = \frac{1}{4}(492)\\
& = 123
\end{align}
$$

Model A is better due to its smaller MSE
### Question C
#### Question I
![[complexity_vs_error|700]]
#### Question II
**High bias = underfitting region**
- Look for both high training error and high testing error region
**High variance = overfitting region**
- Look for low training error but high testing error

High bias occurs when the model is too simple(*not expressive enough*) relative to the problem. This results in high cross-validation error and high training error. 

High variance occurs when the model is too complex relative to the problem. This results in high cross-validation error and low training error. 
#### Question II
1. Reduce the feature's dimensionality. 
2. Perform regularisation
	- Ridge regularisation 
		- Enforce parameters to prefer smaller values and penalise larger values
	- Lasso
	- Elastic net
3. Find more data
	- This does not work with model that underfits
## Question 3
### Question A

| Predicted Score | Actual Label | Predicted Label | TN  | FN  | TP  | FP  |
| --------------- | ------------ | --------------- | --- | --- | --- | --- |
| 0.78            | 1            | 1               |     |     | 1   |     |
| 0.55            | 0            | 1               |     |     |     | 1   |
| 0.42            | 1            | 0               |     | 1   |     |     |
| 0.86            | 1            | 1               |     |     | 1   |     |
| 0.92            | 1            | 1               |     |     | 1   |     |
| 0.47            | 1            | 0               |     | 1   |     |     |
| 0.02            | 0            | 0               | 1   |     |     |     |
| 0.34            | 0            | 0               | 1   |     |     |     |
| 0.89            | 1            | 1               |     |     | 1   |     |
| 0.71            | 1            | 1               |     |     | 1   |     |
| SUM             | <            | <               | 2   | 2   | 5   | 1   |
$$
\begin{align}
\text{Accuracy} &= \frac{7}{10} \\
\text{Precision} &= \frac{5}{6} \\
\text{Recall} &= \frac{5}{7} \\
\text{F}_1 \text{ score} &= \frac{10}{13} \\
\end{align}
$$
### Question B
Decrease the threshold. There will be lesser false negatives
### Question C
![[Past Year Papers/Year 2/Semester 1/Artificial Intelligence Techniques/September 2023#Question 3#Question C]]
### Question D
![[Past Year Papers/Year 2/Semester 1/Artificial Intelligence Techniques/September 2023#Question 3#Question D]]
# Section B
## Question 4
### Question A
#### Question I
$f(x_1, x_2) = 0.1(x_1 - 2) ^2 + 0.2(x_2 - 3)^2$
$$
\begin{align}
f'(x_1) &= 0.1(2)(x_1 -2)(1)\\
& = 0.2(x_1 - 2)  \\
& = 0.2x_1 - 0.4
\end{align}
$$
$$
\begin{align}
f'(x_2) &= 0 + 0.2(2)(x_2 -3)(1) \\
& = 0.4(x_2 - 3) \\
& = 0.4x_2 - 1.2
\end{align}
$$
$$
\begin{align}
x_1 =x_1 - \eta(0.2x_1 - 0.4)\\
x_2 = x_2 - \eta(0.4x_2 - 1.2)
\end{align}
$$
#### Question II
$\eta = 0.5$

| $x_1$ | $x_2$ | $f'(x_1)$ | $f'(x_2)$ | $x'_1$ | $x'_2$ | $f(x_1, x_2)$ |
| ----- | ----- | --------- | --------- | ------ | ------ | ------------- |
| 0     | 0     | -0.4      | -1.2      | 0.2    | 0.6    | 1.476         |
| 0.2   | 0.6   | -0.36     | -0.96     | 0.38   | 1.080  | 1.000         |
| 0.38  | 1.080 | -0.324    | -0.888    | -0.768 | 1.464  | 0.684         |
Yes. The $f(x_1', x_2')$ is decreasing from iteration to iteration. 
### Question B
$h_\theta(x) = \theta_0 + \theta_1(x_1)$ and $\eta = 0.01$
$$
\begin{align}
\bigtriangledown_{\theta} \text{MSE}(\theta) &= \frac{2}{m} \cdot X^T \cdot(X\cdot \theta - y) \\
& = \frac{2}{4}\cdot
\begin{bmatrix} 
1 & 1 & 1 & 1 \\
3 & 5 & 7 & 9 
\end{bmatrix}
\cdot
(\begin{bmatrix} 
1 & 3 \\
1 & 5 \\ 
1 & 7 \\
1 & 9 
\end{bmatrix}
\cdot
\begin{bmatrix}
15 \\
2
\end{bmatrix}
-
\begin{bmatrix}
25 \\
45 \\
53 \\
50
\end{bmatrix}
) \\
& = \frac{2}{4}\cdot
\begin{bmatrix} 
1 & 1 & 1 & 1 \\
3 & 5 & 7 & 9 
\end{bmatrix}
\cdot
(\begin{bmatrix} 
21 \\
25 \\ 
29 \\
33 
\end{bmatrix}
-
\begin{bmatrix}
25 \\
45 \\
53 \\
50\\
\end{bmatrix}
)\\
& = \frac{2}{4}\cdot
\begin{bmatrix} 
1 & 1 & 1 & 1 \\
3 & 5 & 7 & 9 
\end{bmatrix}
\cdot
\begin{bmatrix} 
-4 \\
-20 \\ 
-24 \\
-17 
\end{bmatrix}
\\
& = \frac{2}{4}\cdot
\begin{bmatrix} 
-65 \\
-433
\end{bmatrix}
\\
& =\begin{bmatrix} 
\frac{-65}{2} \\
\frac{-433}{2}
\end{bmatrix}
\\
\end{align}
$$
$$
\begin{align}
\theta &:= \theta - \eta \bigtriangledown\text{MSE}(\theta) \\
& = 
\begin{bmatrix}
15 \\
2
\end{bmatrix}
- 0.01\begin{bmatrix} \frac{-65}{2} \\ \frac{-433}{2}\end{bmatrix} \\
& = 
\begin{bmatrix}
15 \\
2
\end{bmatrix}
- 
\begin{bmatrix} \frac{-13}{40} \\ \frac{-433}{200}\end{bmatrix} \\
& = \begin{bmatrix} 15.325 \\ 4.165\end{bmatrix}
\end{align}
$$
### Question C
#### Question I
Number of classifiers: 10
Advantage: Only 10 classifiers are needed, so it is more computationally efficient and easy to interpret. 
Disadvantage: Data is imbalanced when there are a lot of classes to consider 

### Question II
Number of classifiers: 45
Advantage: Each classifier only needs to be trained on two classes at a time. 
Disadvantage: A lot more classifiers than OvA, so it is slower than OvA. 
## Question 5
### Question A
#### Question I
$$
\begin{align}
P(B) &= 0.2 \\
P(S|B) &= 0.3 \\
P(S|\neg B) &= 0.9 \\
P(\neg S| B) &= 1-0.3 \\ &= 0.7\\
P(\neg S | \neg B) &= 1 - 0.9\\ &= 0.1
\end{align}
$$
#### Question II
$$ 
\begin{align}
P(B, S) &= P(S|B) * P(B) \\
&= 0.3 * 0.2 \\
&= 0.06
\end{align}
$$
#### Question III
$$ 
\begin{align}
P(S) &= P(S, \neg B) + P(S, B) \\
&= (0.9) * (0.8)  + 0.06\\
&= 0.72 + 0.06 \\
&= 0.78
\end{align}
$$
#### Question IV
$$ 
\begin{align}
P(B| \neg S) &= \frac{P(\neg S, B)}{P(\neg S)} \\
& = \frac{0.14}{0.22} \\
&= 0.6364 \\
\end{align}
$$
### Question B
#### Question I
$P(F,S,A) = P(F)\cdot P(S|F) \cdot P(A|S)$
#### Question II
The conditional independence is between A and F such that A is independent of F
#### Question III
$$
\begin{align}
P(f,s,a) &= P(f)\cdot P(s|f) \cdot P(a|s) \\
&= 0.1 \cdot0.8 \cdot0.7 \\
&= 0.056
\end{align}
$$
$$\begin{align}
P(s,a) &= \sum_f P(a|s) \\
&= \sum_f P(f)\cdot P(s|f)\cdot P(a|s)\\
&= (0.1)(0.8)(0.7) + (0.9)(0.05)(0.7)\\
&= 0.056 + 0.0315\\
&= 0.0875
\end{align}
$$
$$\begin{align}
P(\neg a| f,s) &= P(\neg a|s) \\
& = 0.3\\
\end{align}
$$
# See Next
[[Past Year Papers/Year 2/Semester 1/Artificial Intelligence Techniques/September 2023|September 2023]]