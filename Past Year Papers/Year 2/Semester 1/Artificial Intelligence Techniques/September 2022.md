---
aliases:
  - September 2022
tags:
  - PYQ
  - Artificial-Intelligence-Technique
Creation Date: 2024-09-22
Finished Date: 2024-09-23
Completion: true
obsidianUIMode: preview
---
# Section A
## Question 1
### Question A
#### Question I
$$
\begin{align}
P(B) & = 0.2 \\
P(S|B) & = 0.3 \\
P(S|\neg B) &= 0.9 \\
P(\neg S|B) &= 1 - P(S|B) \\
& = 1 - 0.3 \\
& = 0.7 \\
P(\neg S | \neg B) & = 1  - P(S|\neg B) \\
& = 1 - 0.9 \\
& = 0.1
\end{align}
$$
#### Question II
$$
\begin{align}
P(S|B) &= \frac{P(S,B)}{P(B)} \\
0.3 & = \frac{P(S,B)}{0.2} \\
P(S,B) &= 0.06
\end{align}
$$
#### Question III
$$
\begin{align}
P(S) &= P(S, B) + P(S,\neg B) \\
& = 0.06 + (0.9)(0.8) \\
&  = 0.06 + 0.72 \\
& = 0.78
\end{align}
$$
#### Question IV
$$
\begin{align}
P(B|\neg S) &= \frac{P(B, \neg S)}{ P (\neg S)} \\
&= \frac{0.7 \times 0.2}{1-0.78} \\
&= \frac{0.14}{0.22} \\
& = 0.6364
\end{align}
$$
### Question B
#### Question I
$$P(F,S,A) = P(F)\times P(S|F) \times P(A|S)$$
#### Question II
A is dependent on S but independent on F
$A\bot F | S$
#### Question III
$$
\begin{align}
P(f,s,a) &= P(f) \times P(s|f) \times P(a|s) \\
& = 0.1 \times 0.8 \times 0.7 \\
&  = 0.056\\
P(s,a) & = \sum_f P(f) \times P(a|s) \\
& = P(\neg f) \times P(s|\neg f) \times P(a|s) + P(f) \times P(s|f) \times P(a|s) \\
& = 0.056 + 0.1 \times 0.05 \times 0.7 \\
& = 0.0875 \\
P(\neg a|f,s) & = P(\neg a| s) \\
& = 0.3
\end{align}
$$


## Question 2
### Question A
#### Question I
![[bfs|700]]
#### Question II
Path: $A\rightarrow B \rightarrow C \rightarrow F$
Cost: 16
#### Question III
No. BFS is only optimal when the costs increase monotonically from one layer to the next
#### Question IV
10
### Question B
#### Question I
![[Past Year Papers/Year 2/Semester 1/Artificial Intelligence Techniques/Diagrams/december_2023/ucs|700]]
#### Question II
Path: $A\rightarrow D \rightarrow E \rightarrow F$
Cost: 10
#### Question III
Yes. Since UCS always explores the path with the lowest cost.
#### Question IV
6
### Question C
No. There exists a loop in the graph, A and B. Because the nodes are expanded in alphabetical order, this means that both A and B will be added to the front each time, meaning they will be expanded infinitely. DFS doesn't backtrack until it reaches the deepest node and because it is a loop, the deepest node will never be found.
## Question 3
### Question A

| Actual | Predicted | TN  | TP  | FN  | FP  |
| ------ | --------- | --- | --- | --- | --- |
| True   | True      |     | 1   |     |     |
| False  | True      |     |     |     | 1   |
| True   | False     |     |     | 1   |     |
| True   | True      |     | 1   |     |     |
| True   | True      |     | 1   |     |     |
| True   | False     |     |     | 1   |     |
| False  | False     | 1   |     |     |     |
| False  | True      |     |     |     | 1   |
| True   | True      |     | 1   |     |     |
| True   | False     |     |     | 1   |     |
| sum    | <         | 1   | 4   | 3   | 2   |

|     | TN  | TP  |
| --- | --- | --- |
| TN  | 1   | 2   |
| TP  | 3   | 4   |
$$
\begin{align}
\text{Accuracy} &= \frac{5}{10} \\
& = \frac{1}{2} \\
\text{Precision} & = \frac{4}{6} \\
& = \frac{2}{3} \\
\text{Recall} & = \frac{4}{7} \\
\text{F}_1 \text{ score} & = \frac{2}{\frac{1}{precision} + \frac{1}{recall}} \\
& = \frac{2}{\frac{3}{2} + \frac{7}{4}} \\
& = \frac{2}{\frac{13}{4}} \\
& = \frac{8}{13}
\end{align}
$$
### Question B
Recall is more important. This is because we want the system to catch all of the intruders. And any mistakes can be identified manually. Therefore, reducing the threshold should be good.
### Question C
#### Question I
![[complexity_vs_error]]
*Red is **high bias*** and *orange is **high variance***
#### Question II
High bias occurs when the model is too simple to relative to the problem. Consequently, the training error and cross-validation error are high
High variance occurs when the model is too complex to handle the problem. The model "memorises" the training data and does not generalise well to new and foreign data. Consequently, the training error is low but the cross-validation error is high. 
#### Question III
1. Find more data
2. Add restraints to the data
3. Perform dimensionality reduction
### Question D
#### Question I
Number: 10
Advantage: Only need 10 classifiers so easier to interpret and compute. Usually the default
Disadvantage: Data is not well balanced especially when the class is huge
#### Question II
Number: $\frac{10(10-1)}{2} = 45$
Advantage: Each classifier only has to be trained on two classes at a time, so training is simpler
Disadvantage: Due to the number of classifiers, it takes more computing power

# Section B
## Question 4
### Question A
#### Question I
$$
\begin{align}
h_\theta(x) = \sigma(X\cdot \theta) = \frac{1}{1 + e ^{X\cdot \theta}}
\end{align}
$$
*Model A*
$$
\begin{align}
X\cdot \theta & = 
\begin{bmatrix}
1 & 3 \\
1 & 5 \\
1 & 7 \\
1 & 9 \\
\end{bmatrix}
\times
\begin{bmatrix}
-3 \\
0.5
\end{bmatrix}
\\
& =
\begin{bmatrix}
-1.5 \\
-0.5\\
0.5\\
1.5\\
\end{bmatrix}
\end{align}
$$

| x   | $\sigma (X \cdot \theta)$ | $\hat y (\geq 0.5)$ | y   |
| --- | ------------------------- | ------------------- | --- |
| 3   | 0.1824                    | 0                   | 0   |
| 5   | 0.3775                    | 0                   | 0   |
| 7   | 0.6225                    | 1                   | 1   |
| 9   | 0.8176                    | 1                   | 1   |
Accuracy = $\frac{4}{4}$

*Model B*
$$
\begin{align}
X\cdot \theta & = 
\begin{bmatrix}
1 & 3 \\
1 & 5 \\
1 & 7 \\
1 & 9 \\
\end{bmatrix}
\times
\begin{bmatrix}
-1 \\
0.3
\end{bmatrix}
\\
& =
\begin{bmatrix}
-0.1 \\
0.5\\
1.1\\\
3.7\\
\end{bmatrix}
\end{align}
$$

| x   | $\sigma (X \cdot \theta)$ | $\hat y (\geq 0.5)$ | y   |
| --- | ------------------------- | ------------------- | --- |
| 3   | 0.4750                    | 0                   | 0   |
| 5   | 0.6225                    | 1                   | 1   |
| 7   | 0.7503                    | 1                   | 1   |
| 9   | 0.9759                    | 1                   | 1   |
Accuracy = $\frac{3}{4}$
#### Question II
$$
\begin{align}
h_{\theta}(x) & = 
\begin{bmatrix}
0.4750 \\
0.6225 \\
0.7503 \\
0.9759 
\end{bmatrix} \qquad
X = 
\begin{bmatrix}
1 & 3 \\ 
1 & 5 \\
1 & 7 \\
1 & 9 
\end{bmatrix} \qquad
X^T =
\begin{bmatrix}
1 & 1 & 1 &1 \\
3 & 5 & 7 & 9
\end{bmatrix} \\
\end{align}
$$
$$
\begin{align}
\bigtriangledown_{\theta} \text{MSE}(\theta) &= \frac{1}{m} \cdot X^T \cdot(h_\theta(x) - y) \\
(h_\theta(x) - y) & = 
\begin{bmatrix}
0.4750 \\
0.6225 \\
0.7503 \\
0.9759 
\end{bmatrix} 
-
 \begin{bmatrix}
0 \\ 
0 \\
1 \\
1 
\end{bmatrix}\\
& = 
\begin{bmatrix}
0.4750 \\
0.6225 \\
-0.2497 \\
-0.0241 
\end{bmatrix}\\
X^T \cdot (h_\theta(x) - y) & = 
\begin{bmatrix}
1 & 1 & 1 &1 \\
3 & 5 & 7 & 9
\end{bmatrix} 
\cdot
\begin{bmatrix}
0.4750 \\
0.6225 \\
-0.2497 \\
-0.0241 
\end{bmatrix} \\
& = \begin{bmatrix}
0.8237 \\
2.5727 \\
\end{bmatrix} \\
\bigtriangledown_{\theta} \text{MSE}(\theta) &= \frac{1}{4} 
\cdot
\begin{bmatrix}
0.8237 \\
2.5727
\end{bmatrix} \\
& = 
\begin{bmatrix}
0.2059 \\
0.6432 
\end{bmatrix} \\\\
\theta' &= \theta - \eta\bigtriangledown\text{MSE}(\theta)\\
& = 
\begin{bmatrix}
-1 \\
0.3
\end{bmatrix}
- (0.01)
\begin{bmatrix}
0.2059 \\
0.6432 
\end{bmatrix} \\
& = 
\begin{bmatrix}
-1.0021 \\
0.2936 
\end{bmatrix}
\end{align}
$$

### Question B
#### Question I
$$
\begin{align}
x' = \frac{\text{x - min}}{\text{max - min}}
\end{align}
$$

| x   | x'            |
| --- | ------------- |
| 3   | 0             |
| 5   | $\frac{1}{3}$ |
| 7   | $\frac{2}{3}$ |
| 9   | 1             |
#### Question II
$$
\begin{align}
\sigma &= \sqrt{\frac{(x - \mu)^2}{N}} \\
\mu & = \frac{\sum x}{N}\\
&  = \frac{24}{4} \\
& = 6
\end{align}
$$

| x   | x'      |
| --- | ------- |
| 3   | -1.3416 |
| 5   | -0.4472 |
| 7   | 0.4472  |
| 9   | 1.3416  |
## Question 5
### Question A
#### Question I
*Model A*
$$
\begin{align}
\text{MSE} & = \frac{1}{m} \cdot (h_\theta(X) - y)^2 \\
h_\theta(x) & = X\cdot \theta \\
& = 
\begin{bmatrix}
1 & 85\\
1 & 80 \\
1 & 75 \\
1 & 71 \\
1 & 69
\end{bmatrix}
\cdot
\begin{bmatrix}
-1000 \\
20
\end{bmatrix} \\
& = 
\begin{bmatrix}
700\\
600\\
500\\
420\\
380
\end{bmatrix} \\
h_\theta(x) - y 
& = 
\begin{bmatrix}
700\\
600\\
500\\
420\\
380
\end{bmatrix} 
-
\begin{bmatrix}
600 \\
530 \\
300 \\ 
240 \\
250 
\end{bmatrix} \\
& = \begin{bmatrix}
100 \\
70 \\
200 \\ 
180 \\
130 
\end{bmatrix} \\
(h_\theta(x) - y )^2 & = (h_\theta(x) - y ) \times (h_\theta(x) - y )^T \\
& = \begin{bmatrix}
100 \\
70 \\
200 \\ 
180 \\
130 
\end{bmatrix}
\times 
\begin{bmatrix}
100 &
70 &
200 & 
180 &
130 
\end{bmatrix} \\
& = 100^2 + 70^2 + 200 ^2 + 180^2 + 130 ^ 2 \\
& = 104,200\\
\text{MSE} & = \frac{1}{5} \cdot 104,200 \\
& = 20,840
\end{align}
$$

*Model B*
$$
\begin{align}
\text{MSE} & = \frac{1}{m} \cdot (h_\theta(X) - y)^2 \\
h_\theta(x) & = X\cdot \theta \\
& = 
\begin{bmatrix}
1 & 85\\
1 & 80 \\
1 & 75 \\
1 & 71 \\
1 & 69
\end{bmatrix}
\cdot
\begin{bmatrix}
-1500 \\
25
\end{bmatrix} \\
& = 
\begin{bmatrix}
625\\
500\\
375\\
275\\
225
\end{bmatrix} \\
h_\theta(x) - y 
& = 
\begin{bmatrix}
625\\
500\\
375\\
275\\
225
\end{bmatrix} 
-
\begin{bmatrix}
600 \\
530 \\
300 \\ 
240 \\
250 
\end{bmatrix} \\
& = \begin{bmatrix}
25\\
-30 \\
75 \\ 
35 \\
-25 
\end{bmatrix} \\
(h_\theta(x) - y )^2 & = (h_\theta(x) - y ) \times (h_\theta(x) - y )^T \\
& =  \begin{bmatrix}
25\\
-30 \\
75 \\ 
35 \\
-25 
\end{bmatrix}
\times 
\begin{bmatrix}
25 &
-30 &
75 & 
35 &
-25 
\end{bmatrix} \\
& = 25^2 + (-30)^2 + 75^2 + 35^2 + (-25)^ 2 \\
& = 9,000\\
\text{MSE} & = \frac{1}{5} \cdot 9,000 \\
& = 1,800
\end{align}
$$

Model B is better
#### Question II
$$
\begin{align}
X ^ T &=  \begin{bmatrix}
1 & 1 & 1 & 1 & 1\\
85 & 80 & 75 & 71 & 69
\end{bmatrix} \\
\end{align}
$$
$$
\begin{align}
\bigtriangledown_{\theta} \text{MSE}(\theta) &= \frac{2}{m} \cdot X^T \cdot(h_\theta(x) - y) \\
h_\theta(x) - y 
& = \begin{bmatrix}
100 \\
70 \\
200 \\ 
180 \\
130 
\end{bmatrix} \\
\bigtriangledown_\theta\text{MSE}(\theta) & = \frac{2}{5} \cdot \begin{bmatrix}
1 & 1 & 1 & 1 & 1\\
85 & 80 & 75 & 71 & 69
\end{bmatrix} 
\cdot
\begin{bmatrix}
100 \\
70 \\
200 \\ 
180 \\
130 
\end{bmatrix} \\
& = \frac{2}{5} \cdot \begin{bmatrix}
680 \\
50850
\end{bmatrix}\\
& =\begin{bmatrix}
272 \\
20,340
\end{bmatrix} \\\\
\theta' & = \theta - \eta \bigtriangledown_\theta\text{MSE}(\theta) \\
& = \begin{bmatrix}
-1000 \\
20
\end{bmatrix} -
0.0001 (
\begin{bmatrix}
272 \\
20,340
\end{bmatrix}
)\\
& = \begin{bmatrix}
-1000 \\
20
\end{bmatrix} -
\begin{bmatrix}
0.0272 \\
2.0232
\end{bmatrix}\\
& = 
\begin{bmatrix}
-1000.03 \\
17.966
\end{bmatrix}
\end{align}
$$
### Question B
#### Question I
$\text{distance} = \frac{High-Low}{N} = \frac{600-240}{2} = 180$


| y   | Discrete |
| --- | -------- |
| 600 | High     |
| 530 | High     |
| 300 | Low      |
| 240 | Low      |
| 250 | Low      |
#### Question II
$$
\begin{align}
h_\theta(x) & = X\cdot \theta \\
& = 
\begin{bmatrix}
1 & 85\\
1 & 80 \\
1 & 75 \\
1 & 71 \\
1 & 69
\end{bmatrix}
\cdot
\begin{bmatrix}
-7.4 \\
0.1
\end{bmatrix} \\
&= 
\begin{bmatrix}
1.1 \\
0.6 \\
0.1 \\
-0.3 \\
-0.5
\end{bmatrix}
\end{align}
$$

| x   | $h_\theta(x)$ | $\hat y$ | y   |
| --- | ------------- | -------- | --- |
| 85  | 0.7503        | 1        | 1   |
| 80  | 0.6457        | 1        | 1   |
| 75  | 0.5250        | 1        | 0   |
| 71  | 0.4256        | 0        | 0   |
| 69  | 0.6225        | 1        | 0   |
Accuracy = $\frac{3}{5}$

# Next Paper
[[Past Year Papers/Year 2/Semester 1/Artificial Intelligence Techniques/May 2022|May 2022]]