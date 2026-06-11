---
obsidianUIMode: preview
---

# Question One

Prove $$\forall c \cdot \exists n_0  = \max(\lceil \frac{1}{c}\rceil, 20,001) + 1\cdot \forall n > n_0 \cdot n^{10000} < cn!$$
Since $$n>\lceil \frac{1}{c}\rceil +1$$

$$
\begin{align}
n &>\frac{1}{c} \\
& cn > 1 \text{ and } k(n-k+1) > n \text{ for } k = 2,3,4,...,n-1 \\
&\text{Since } n > 20,001; \quad 2(n-1) \geq n, 3(n-2) \geq n,..., 10,001(n-10,000) \\
& \text{Therefore, } \\
& n^{10,000} < (cn)(2(n-1))(3(n-2))...(10,000(n-9999))(10,001(n-10,000))\\
& n^{10,000} < (1)(2)(3)...(10,000)(10,001)(n-10,000)...(n-2)(n-1)(n) \\
& n^{10,000} < c(1)(2)(3)...(10,000)(10,001)[10,002...(n-10,001)]...(n-10,000)(n-2)(n-1)(n) \\
& n^{10,000} < cn!
\end{align}
$$

$$
\begin{align}
& \text{for } k = 2,...,n-1 \\
& n > k > 1 \\
& n>k \text{ and } k>1 \\
& (n-k)(k-1) > 0 \\
& nk - k^2 + k - n > 0 \\
& k(n-k+1) > n
\end{align}
$$

# Question Two

## Question A

$$T(n) = 3T(\frac{n}{6}) + \frac{n}{\log n}$$
$a = 3 \text{, } b= 6, \text{, } f(n) = \frac{n}{\log n} \text{, } \exists \epsilon = \frac{1- \log_6 3}{2}$
$$f(n) = \frac{n}{\log n} \geq n^{\frac{\log_63 +1}{2}} = n ^{\log_63 + \frac{1- \log_63}{2}} = n ^{\log_b a + \epsilon}$$
$f(n) = \Omega{(n^{\log_b a + \epsilon})}$

_Regularity Condition_

$\exists C = \frac{2}{3} < 1$
$$af(\frac{n}{b}) = 3(\frac{\frac{n}{6}}{\log \frac{n}{6}}) = \frac{1}{2}(\frac{n}{\log {\frac{n}{6}}}) \leq c (\frac{n}{ \log n})$$
_Proof_
$\text{let } n \geq 6^4$

$$
\begin{align}
\log {n} \geq 4 \cdot \log 6 \\
4 \cdot \log 6 \leq \log {n}  \\
4 \cdot \log 6 \leq 4\cdot \log {n} - 3 \cdot \log n  \\
3 \cdot \log n \leq 4\cdot \log {n} - 4 \cdot \log 6 \\
3 \cdot \log n \leq4(\log {\frac{n}{6}}) & \text{divide with 6} \\
\frac{1}{2} \log n \leq \frac{2}{3} (\log {\frac{n}{6}}) \\
\frac{1}{2} \log n \leq c \cdot (\log {\frac{n}{6}}) \\
\frac{\frac{1}{2}}{\log {\frac{n}{6}}} \leq \frac{c}{\log n} & \text{multiply by n again} \\
\frac{\frac{1}{2} n}{\log {\frac{n}{6}}} \leq \frac{cn}{\log n}
\end{align}
$$

Case 3 applies

$$
\begin{align}
&& T(n) = \theta{(f(n))} \\
&& = \theta(\frac{n}{\log n}) \\
&& = O(\frac{n}{\log n})
\end{align}
$$

## Question B

$$T(n) = 9T(\frac{n}{6}) + n\log^2 n$$
$a = 3 \text{, } b= 6, \text{, } f(n) = n \log^2 n \text{, } \exists \epsilon = \frac{\log_6 9 - 1}{2}$
$$f(n) = n\log^2 n \leq n^{\frac{\log_69 +1}{2}} = n ^{\log_69 + \frac{\log_69 - 1}{2}} = n ^{\log_b a - \epsilon}$$
$f(n) = O(n ^{\log_b a - \epsilon})$
Case 1 applies

$$
\begin{align}
&& T(n) = \theta{(n ^{\log_b a})} \\
&& = \theta(n^{log_69}) \\
&& = O(n^{\log_69})
\end{align}
$$

## Question C

$$T(n) = 9T(\frac{n}{6}) + n\log^2 n$$
Claim: $T(n) < cn^{\log_69}$

$$
\begin{align}
T(n) &= 9T(\frac{n}{6}) + n \log^2 n \\
& < 9 c(\frac{n}{6})^{\log_69}+n \log^2 n \\
& = 9 c(\frac{n^{\log_69}}{6^{\log_69}})+n \log^2 n \\
& = 9 c(\frac{n^{\log_69}}{9})+n \log^2 n \\
& = c(n^{\log_69})+n \log^2 n \quad < c(n^{\log_69})\\
\end{align}
$$

The claim is false
New claim: Claim: $T(n) < cn^{\log_69} - c'n \log^2n$ $c>c' \quad c' > 2$

$$
\begin{align}
T(n) &= 9T(\frac{n}{6}) + n \log^2 n \\
& < 9 [ c(\frac{n}{6})^{\log_69} - c'\frac{n}{6}\log^2(\frac{n}{6})]+n \log^2 n \\
& = cn^{\log_69} - \frac{3}{2}c'n\log^2\frac{n}{6} + n \log^2n \\
& = cn^{\log_69} - \frac{3}{2}c'n(\log n - \log 6)^2+ n \log^2n \\
& = cn^{\log_69} - \frac{3}{2}c'n(\log^2n - 2\log n \log 6 + \log^2 6)+ n \log^2n \\
&  = cn^{\log_69} - \frac{3}{2}c'n\log^2n + 3 c'n\log n \log 6 - \frac{3}{2}c'n\log^26 + n\log^2 n \\
& = cn^{\log_69} - c'n\log^2n  - \frac{1}{2}c'n\log^2n+ 3 c'n\log n \log 6 - \frac{3}{2}c'n\log^26 + n\log^2 n \\
& < cn^{\log_69} - c'n\log^2n
\end{align}
$$

$$
\begin{align}
\text{let n } &> 2^{\frac{3c'\log6}{\frac{1}{2}c' -1}} \\
& n > 2 ^ {\frac{3c'\log6}{\frac{1}{2}c' -1}} \\
& \log n > \frac{3c'\log6}{\frac{1}{2}c' -1} \\
& (\frac{1}{2}c' - 1) \log n > 3c' \log 6 \\
& \frac{1}{2}c' \log n - \log n > 3c' \log 6 \\
& \frac{1}{2}c' \log n - \log n - 3c' \log 6 > 0  \qquad\text{multiply by } n \log n\\
& \frac{1}{2}c'n \log^2 n - n\log^2 n - 3c'n\log 6 \log n > 0 \\
& \frac{1}{2}c'n \log^2 n - 3c'n\log 6 \log n + c'n(\frac{3}{2}) \log^2 6- n\log^2 n> 0 \\
& \frac{1}{2}c'n \log^2 n - c'n[3\log 6 \log n - (\frac{3}{2}) \log^2 6]- n\log^2 n > 0 \\
& -\frac{1}{2}c'n \log^2 n + c'n[3\log 6 \log n - (\frac{3}{2}) \log^2 6]+ n\log^2 n < 0 \\
\end{align}
$$

_Idk if i should put this but_
$cn^{\log_69} - c'n\log^2n - \frac{1}{2}c'n \log^2 n + c'n[3\log 6 \log n - (\frac{3}{2}) \log^2 6]+ n\log^2 n < cn^{\log_69} - c'n\log^2n$
Since $\frac{1}{2}c' -1 > 0$

$$
\begin{align}
\frac{1}{2}c' - 1 > 0 \\
\frac{1}{2}c'>1 \\
c' > 2
\end{align}
$$

Therefore, $c'>2$

# Question Three

## Question A

### Question I

**Base Case**:
If tree, T, is empty, then the height of T is 0
**Recursive Case**:
If tree is not empty, then the height of T is the maximum of the height of the right subtree and the height of the left subtree plus 1

### Question II

```pseudocode
Algorithm height(T)
	IF T is empty return 0
	ELSE
		leftHeight = height(T.left)
		rightHeight = height(T.right)
		return 1 + max(leftHeight, rightHeight)
```

### Question III

Consider a binary tree with $n$ number of nodes. The statement `IF T is empty return 0` takes constant time to evaluate. 2 recursive statements are called with `leftHeight = height(T.left)` and `rightHeight = height(T.right)`. The algorithm calculates height by visiting both left and right subtrees each time. This means that every node in the tree will be visited once. Since each node will be visited once, and each node performs constant time amount of work, and there are n number of nodes, the time complexity is $O(1)*n$. Thus, the time complexity is $O(n)$.

_See lecture notes_

## Question B

**Base case**
Let n = 1
Consider a tree with only 1 node. This means that both left and right pointer of the node are `null`. So, the number of null pointers would be 2.

The statement for the base case is true

**Inductive step**
Assume the statement is true for $n=k \geq 1$
Let n = k+1 When the number of nodes in the binary tree is $k+1$, the number of `null` pointers would be $k+2$.

Consider a tree with $k+1$ number of nodes. Take the leaf node and remove it. This means that the pointer pointing to the leaf node is now a `null` pointer and the number of nodes in the tree is now $(k+1)-1 = k$.

According to the statement, the number of `null` pointers is now $k+1$. The removed leaf node is then returned back to its original place. Then, the pointer which were `null` is now pointing back to the node. Since leaf nodes have no child nodes, both pointers of the returned leaf nodes are `null` pointers. So, the original tree had $(k+1)-1+2$ `null` pointers, or $k+2$ `null` pointers.

Result from induction.

## Question C

$n(N-1)+1$

