---
aliases:
  - December 2022
tags:
  - PYQ
  - Artificial-Intelligence-Technique
Creation Date: 2024-09-17T14:13:00
Finished Date: 2024-09-23
Completion: true
obsidianUIMode: preview
---
# Section A
## Question 1
### Question A
Let student B attendance = B and student T attendance = T
$$
\begin{align}
P(\neg B, \neg T) &= P(\neg B) \times P(\neg T) \\
& = 0.2 \times 0.4 \\
& = 0.08
\end{align}
$$
### Question B
At least one student = B only or T only or both
$$
\begin{align}
P(A) &= P(B, \neg T) + P(\neg B, T) + P(B,T) \\
& = (0.8 \times 0.4)+(0.2 \times 0.6)+( 0.8 \times 0.6) \\
& = 0.32 + 0.12 + 0.48 \\
&  = 0.92
\end{align}
$$
### Question C
$$P(S) = P(A)$$
#### Question I
![[bayes_network|700]]
#### Question II
Yes. Student T attendance does not affect Student B's attendance
#### Question III
$$
\begin{align}
P(B,T,S) = P(B) \times P(T) \times P(S|B,T)
\end{align}
$$
$$
\begin{align}
P(B|S,T) &= \frac{P(B,S,T)}{P(S,T)} 
\end{align}
$$
$$
\begin{align}
P(B,T,S) & = P(B)\times P(T) \times P(S|B,T) \\
& = 0.8 \times 0.6 \times 1 \\
& = 0.48
\end{align}
$$
$$
\begin{align}
P(S,T) & = \sum_B P(S,T) \\
& = \sum_B P(B) \times P(T) \times P(S|B,T) \\
& = P(B) \times P(T) \times P(S|B,T) + P(\neg B) \times P(T) \times P(S|\neg B, T) \\
& = (0.8 \times 0.6 \times 1) + (0.2 \times 0.6 \times 1) \\
& = 0.48 + 0.12 \\
& = 0.60
\end{align}
$$
$$
\begin{align}
P(B|S,T) & = \frac{0.48}{0.60} \\
& = 0.8
\end{align}
$$
## Question 2
### Question A
no mask = negative and mask = positive

| Actual Label | Predicted Label | TN  | FN  | TP  | FP  |
| ------------ | --------------- | --- | --- | --- | --- |
| 1            | 0               |     | 1   |     |     |
| 0            | 0               | 1   |     |     |     |
| 1            | 1               |     |     | 1   |     |
| 0            | 1               |     |     |     | 1   |
| 1            | 0               |     | 1   |     |     |
| 0            | 0               | 1   |     |     |     |
| 1            | 1               |     |     | 1   |     |
| 0            | 0               | 1   |     |     |     |
| 1            | 1               |     |     | 1   |     |
| 1            | 1               |     |     | 1   |     |
| Sum          | <               | 3   | 2   | 4   | 1   |
$$
\begin{align}
\begin{bmatrix}
TN & FP \\
FN & TP
\end{bmatrix} 
= 
\begin{bmatrix}
3 & 1 \\
2 & 4
\end{bmatrix} 
\end{align}
$$
### Question B
$$
\begin{align}
\text{Accuracy} &= \frac{7}{10} \\
\text{Precision} &= \frac{4}{5} \\
\text{Recall} &= \frac{2}{3} \\
\text{F}_1 \text{ score} &= \frac{8}{11} \\
\end{align}
$$
### Question C
Set a random seed. By setting a random seed, the model becomes deterministic and it will produce consistent result across multiple run with the same parameters. This lets the data scientist to evaluate the true performance of the model. Set a random seed during splitting of the sample. 
#### Question D*
The purpose of testing set is to introduce the model to unseen data to test if the can generalise well to unseen data. The evaluation metrics during training can be compared to the evaluation metrics during testing to determine the gap between the training error and the testing error. If the training error is low and testing error is high, overfitting has occurred. The validation sets serve as intermediary test sets to see if the model has overfitted during training and serve as guides on decision making regarding the tuning the model's complexity before the final evaluation on the test set.
## Question 3
### Question A
#### Question I
![[a_search|700]]
#### Question II
Path: $A\rightarrow B \rightarrow C \rightarrow H \rightarrow G$
Cost: 5
#### Question III
Yes. The true cost is the same as the predicted cost

>[!REMINDER] Admissible
>*You're optimistic and thinks **it's not that bad***
>The prediction cost is $\leq$ the true cost
#### Question IV
6 nodes
### Question B
Repeated expansion on the same node. Since the graph state is undirected, there are scenarios where the same node is expanded twice.
### Question C
There will be an increase in computation time and memory usage. Since the algorithm may explore a lot of unnecessary nodes before reaching the goal, thereby taking longer time. This is because the algorithm underestimates the cost to reach the goal. This makes the algorithm less efficient than it should be. 
# Section B
## Question 4
### Question A
#### Question I
*Model A*
$$
\begin{align}
\text{MSE} &= \frac{1}{m} (h_\theta(x) - y)^2 \\
& = \frac{1}{5} (h_\theta(x) - y)^2 \\
\end{align}
$$
$$
\begin{align}
h_\theta(x)  = X\cdot \theta &= 
\begin{bmatrix}
1 & 81 \\
1 & 80 \\
1 & 75 \\
1 & 71 \\
1 & 69
\end{bmatrix}
\cdot
\begin{bmatrix}
-1700 \\ 
27
\end{bmatrix}
\\
& = 
\begin{bmatrix}
487 \\
460 \\
325 \\
217 \\
163 \\
\end{bmatrix}
\end{align}
$$
$$
\begin{align}
\text{MSE} &= \frac{1}{m} (h_\theta(x) - y)^2 \\
& = \frac{1}{5} (\begin{bmatrix}
487 \\
460 \\
325 \\
217 \\
163 \\
\end{bmatrix} 
-
\begin{bmatrix}
609.9 \\
536.7 \\
323.1 \\
237.4 \\
266.3 \\
\end{bmatrix})^2 \\
& = \frac{1}{5}(
\begin{bmatrix}
-122.9 \\
-76.7 \\
1.9\\
-20.4 \\
-103.3 \\
\end{bmatrix}
)^2 \\
& = \frac{1}{5}(
\begin{bmatrix}
-122.9 & -76.7 & 1.9 & -20.4 & -103.3 
\end{bmatrix}
\begin{bmatrix}
-122.9 \\
-76.7 \\
1.9\\
-20.4 \\
-103.3 \\
\end{bmatrix}
)\\
& = \frac{1}{5} (32077.96) \\
& = 6415.592
\end{align}
$$
*Model B*
$$
\begin{align}
h_\theta(x)  = X\cdot \theta &= 
\begin{bmatrix}
1 & 81 \\
1 & 80 \\
1 & 75 \\
1 & 71 \\
1 & 69
\end{bmatrix}
\cdot
\begin{bmatrix}
200 \\ 
10
\end{bmatrix}
\\
& = 
\begin{bmatrix}
1010 \\
1000 \\
950 \\
910 \\
890 \\
\end{bmatrix}
\end{align}
$$
$$
\begin{align}
\text{MSE} &= \frac{1}{m} (h_\theta(x) - y)^2 \\
& = \frac{1}{5} (\begin{bmatrix}
1010 \\
1000 \\
950 \\
910 \\
890 \\
\end{bmatrix}
-
\begin{bmatrix}
609.9 \\
536.7 \\
323.1 \\
237.4 \\
266.3 \\
\end{bmatrix})^2 \\
& = \frac{1}{5}(
\begin{bmatrix}
400.1 \\
463.3 \\
626.9\\
672.6 \\
623.7\\
\end{bmatrix}
)^2 \\
& = \frac{1}{5}(
\begin{bmatrix}
400.1& 463.3 & 626.9 & 672.6 & 623.7 
\end{bmatrix}
\begin{bmatrix}
400.1 \\
463.3 \\
626.9\\
672.6 \\
623.7\\
\end{bmatrix}
)\\
& = \frac{1}{5} (1,609,122.96) \\
& = 321824.59
\end{align}
$$
Model A is better
#### Question II
$$
\begin{align}
\bigtriangledown_{\theta} \text{MSE}(\theta) &= \frac{2}{m} \cdot X^T \cdot(X\cdot \theta - y) \\
& = \frac{2}{5}\cdot 
\begin{bmatrix} 
1 & 1 & 1 & 1 & 1 \\
81 & 80 & 75 & 71 & 69 
\end{bmatrix}
\cdot
(
\begin{bmatrix}
1 & 81 \\
1 & 80 \\
1 & 75 \\
1 & 71 \\
1 & 69
\end{bmatrix}
\cdot 
\begin{bmatrix}
200 \\
10
\end{bmatrix}
-
\begin{bmatrix}
609.9 \\
536.7 \\
323.1 \\
237.4 \\
266.3 \\
\end{bmatrix}
) \\
& = \frac{2}{5}\cdot 
\begin{bmatrix} 
1 & 1 & 1 & 1 & 1 \\
81 & 80 & 75 & 71 & 69 
\end{bmatrix}
\cdot
(
\begin{bmatrix}
400.1 \\
463.3 \\
626.9\\
672.6 \\
623.7\\
\end{bmatrix}
) \\
& = \frac{2}{5} \cdot 
\begin{bmatrix}
2786.6 \\
207279.5
\end{bmatrix}\\ 
& = \begin{bmatrix}
1114.64 \\
82911.8
\end{bmatrix}\\ 
\end{align}
$$
$$
\begin{align}
\theta' &= \theta - \bigtriangledown_{\theta} \text{MSE}(\theta) \\
& = 
\begin{bmatrix}
200\\ 10
\end{bmatrix}
- 
\begin{bmatrix}
1114.64 \\
82911.8
\end{bmatrix}\\ 
& = 
\begin{bmatrix}
-914.64 \\
-82901.8
\end{bmatrix}
\end{align}
$$
#### Question III
No. The entire data points will be looked at all at once to calculate the gradient at each step, so the order of the data does not matter.
### Question B
If the learning rate is too high, the algorithm may not converge at a local minima. The algorithm may just overshoot. 
### Question C
1. Does not scale well with the number of samples
	1. If the number of samples is high, computation time will be slower since the gradient is computed with the entire set at each step. 
## Question 5
### Question A
$$
X= \begin{bmatrix}
1 & 3\\
1 & 5 \\
1 & 7 \\
1 & 9 \\
\end{bmatrix}
\qquad X^T = 
\begin{bmatrix}
1 & 1 & 1 & 1\\
3 & 5 & 7 & 9 \\
\end{bmatrix}
\qquad
y = 
\begin{bmatrix}
0 \\0\\1\\1
\end{bmatrix}
\qquad
\theta =
\begin{bmatrix}
-3 \\ 0.5
\end{bmatrix}
$$
$$\sigma(X\cdot\theta) = \frac{1}{1+ e^{-X\cdot \theta}}$$
#### Question A
*Model A*

$$
\begin{align}
-X\cdot\theta &= -(\begin{bmatrix}
1 & 3\\
1 & 5 \\
1 & 7 \\
1 & 9 \\
\end{bmatrix}
\cdot
\begin{bmatrix}
-3 \\ 0.5
\end{bmatrix}) \\
&=
-(\begin{bmatrix}
-1.5 \\
-0.5 \\
0.5 \\
1.5
\end{bmatrix}) \\
&=
\begin{bmatrix}
1.5 \\
0.5 \\
-0.5 \\
-1.5
\end{bmatrix} \\
\end{align}
$$

| x   | $h_\theta(x)$ | $\hat{y} \geq 0.5$ | $y$ |
| --- | ------------- | ------------------ | --- |
| 3   | 0.1824        | no                 | no  |
| 5   | 0.3775        | no                 | no  |
| 7   | 0.6225        | yes                | yes |
| 9   | 0.8176        | yes                | yes |
Accuracy = 4/4

*Model B*
$$
\begin{align}
-X\cdot\theta &= -(\begin{bmatrix}
1 & 3\\
1 & 5 \\
1 & 7 \\
1 & 9 \\
\end{bmatrix}
\cdot
\begin{bmatrix}
-1 \\ 0.3
\end{bmatrix}) \\
&=
-(\begin{bmatrix}
-0.1\\
0.5 \\
1.1 \\
1.7
\end{bmatrix}) \\
&=
\begin{bmatrix}
0.1 \\
-0.5 \\
-1.1 \\
-1.7
\end{bmatrix} \\
\end{align}
$$

| x   | $h_\theta(x)$ | $\hat{y} \geq 0.5$ | y   |
| --- | ------------- | ------------------ | --- |
| 3   | 0.4750        | no                 | no  |
| 5   | 0.6225        | yes                | no  |
| 7   | 0.7503        | false              | yes |
| 9   | 0.8455        | false              | yes |
Accuracy = 3/4
#### Question II
*Use model B*
$$
\begin{align}
\bigtriangledown MSE(\theta) &= \frac{2}{m} \cdot X^T \cdot (h_\theta(x) - y) \\
& = \frac{2}{4} \cdot \begin{bmatrix}
1 & 1 & 1 & 1\\
3 & 5 & 7 & 9 \\
\end{bmatrix} 
\cdot 
(
\begin{bmatrix}
0.4750 \\
0.6225 \\
0.7503\\
0.8455
\end{bmatrix}
-
\begin{bmatrix}
0 \\0\\1\\1
\end{bmatrix}
)\\
& = \frac{2}{4} \cdot \begin{bmatrix}
1 & 1 & 1 & 1\\
3 & 5 & 7 & 9 \\
\end{bmatrix} 
\cdot 
(
\begin{bmatrix}
0.4750 \\
0.6225\\
-0.2497 \\
-0.1545
\end{bmatrix}
)\\
& = \frac{2}{4} \cdot \begin{bmatrix}
0.6933\\
1..3990 \\
\end{bmatrix} \\
& = \begin{bmatrix}
0.1733\\
0.3497
\end{bmatrix} \\
\end{align}
$$
$$ 
\begin{align}
\theta' & = \theta - \eta\bigtriangledown\text{MSE}(\theta) \\
& = 
\begin{bmatrix} 
-1 \\ 0.3
\end{bmatrix}
- (0.01)
\begin{bmatrix} 
0.1733\\
0.3497
\end{bmatrix}\\
& = 
\begin{bmatrix} 
-1.0017\\
0.2965
\end{bmatrix}
\end{align}
$$
#### Question III
Yes. Since, this helps the algorithm from getting stuck in a local minima. By shuffling, we can break any patterns that lead to that local minima and increases the chance of finding a global minima.

Shuffling introduces randomness and forces the algorithm to explore a wider region, increasing the chance of finding a global minima.
### Question B
The algorithm will converge but it will take a long time.
### Question C
It scales well with the number of features. Much faster than normal equation when the number of features increases.
# See next
[[Past Year Papers/Year 2/Semester 1/Artificial Intelligence Techniques/September 2022|September 2022]]