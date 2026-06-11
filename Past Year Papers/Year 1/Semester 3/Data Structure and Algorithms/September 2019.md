---
aliases:
  - September 2019
tags:
  - PYQ
  - DSA
Creation Date: 2024-05-22T13:39:00
Completion: true
obsidianUIMode: preview
---
# Section A
## Question 1

### Question A

| <span class ="green">I</span>   | c                                               |
| ------------------------------- | ----------------------------------------------- |
| <span class ="green">II</span>  | Error                                           |
| <span class ="green">III</span> | 8                                               |
| <span class ="green">IV</span>  | error. ptr is a pointer. ptr.age will not work. |

### Question B
![[Past Year Papers/Year 1/Semester 3/Data Structure and Algorithms/Diagrams/september_2019/linked_list|5000]]

### Question C
```cpp
bool List::swapValues(int n){
	// swap value in node n with the first node in the list
	// n must be a valid value since it indicates the node position in the list
	// Use find() to find node in position n
	// function will return false if n is not valid or the function is unable to find node n 
	if (n < 1 || n > count) return 0;
	Node* front{ head };
	Node* replace{ find(n) };
	Node* pre{ find(n-1) };
	
	head->next = replace;
	pre->next = front;
	front->next = replace->next;
	
	return 1;
}
```

## Question 2
### Question A
![[name_stack|5000]]
### Question B
![[fruit_queue|1000]]

---
### Question C
#### Question I
![[number_stack|5000]]
#### Question II
![[Past Year Papers/Year 1/Semester 3/Data Structure and Algorithms/Diagrams/september_2019/number_queue|5000]]
## Question 3
### Question A
#### Question I

| 76  | 13  | 90  | 65  | 6   | 37  | 82  | index = 0 |
| --- | --- | --- | --- | --- | --- | --- | --------- |
| 65  | 13  | 90  | 76  | 6   | 37  | 82  | index = 0 |
| 65  | 13  | 90  | 76  | 6   | 37  | 82  | index = 1 |
| 65  | 13  | 90  | 76  | 6   | 37  | 82  | index = 1 |
| 65  | 13  | 90  | 76  | 6   | 37  | 82  | index = 1 |
| 65  | 13  | 6   | 76  | 90  | 37  | 82  | index = 2 |
| 65  | 13  | 6   | 37  | 90  | 76  | 82  | index = 3 |
| 65  | 13  | 6   | 37  | 90  | 76  | 82  | index = 3 |
| 37  | 13  | 6   | 65  | 90  | 76  | 82  | index = 3 |

#### Question II


| Sorting Methods | Best Case           | Worst Case       |
| --------------- | ------------------- | ---------------- |
| Bubble Sort     | $O(N)$              | $O(N^2)$         |
| Merge Sort      | $O(N\; log_2 \; N)$ | $O(N\;log_2\;N)$ |
| Not available   | $O(N^2)$            | $O(N^2)$         |
| Not available   | $O(log_2\;N)$       | $O(N)$           |
| Quick Sort      | $O(N\;log_2\;N)$    | $O(N^2)$         |
### Question B
#### Recursive method 
```CPP
bool binarySearch(int array[], int key,int end, int start){
	if (end >= start){
		int mid{ (end+start)/2 };
		if (array[mid] == key)
			return 1;
		else if(array[mid] > key)
			return binarySearch(array, key, mid-1, start);
		return binary Search(array, key, mid+1, start);
	}
	return 0;
}
```
#### Iterative method
```CPP
bool binarySearch(int array[], int key int end, int start){
	int mid{};
	while(start <= end){
		mid = (start+end)/2;
		if(array[mid] == key)
			return 1;
		else if(array[mid] > key)
			end = --mid;
		else
			start = ++mid;
	}
	return 0;
}
```
![[Past Year Papers/Year 1/Semester 3/Data Structure and Algorithms/Diagrams/september_2019/binary_search|binary_search]]
### Question C
#### Question I
$O(n)$
#### Question II
>[!NOTE] Floyd's algorithm/Hare and rabbit algorithm
>Refer to note to see the algorithms applied

$$\begin{align}
& (O(n) * O(n)) + O(n) \\
& O(n^2) + O(n) \\ 
& O(n^2)
\end{align}$$
$O(n)$ works too. (different reasoning)
#### Question III
$O(n)$
# Section B
## Question A
#### Question I
![[Past Year Papers/Year 1/Semester 3/Data Structure and Algorithms/Diagrams/september_2019/bst|750]]
### Question B
#### Question I

>[!NOTE] BFS 
>Remember the coding for this
To output each level of the tree
#### Question II
![[bsf|1000]]
