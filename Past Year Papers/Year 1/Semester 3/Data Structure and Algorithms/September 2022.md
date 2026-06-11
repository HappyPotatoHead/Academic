---
aliases:
  - Septembr 2022
tags:
  - PYQ
  - DSA
Creation Date: 2024-05-22T13:40:00
Completion: true
obsidianUIMode: preview
---
# Section A
## Question 1 
![[Past Year Papers/Year 1/Semester 3/Data Structure and Algorithms/September 2023#Question 1|September 2023]]

## Question 2
### Question A
#### Question I
![[Past Year Papers/Year 1/Semester 3/Data Structure and Algorithms/Diagrams/september_2022/stack|150]]
#### Question II
*I draw it like this for convenience*
![[Past Year Papers/Year 1/Semester 3/Data Structure and Algorithms/Diagrams/september_2022/number_queue|500]]
### Question B
```cpp
bool reverseFirstkElementInQ(Queue *q, int k){
	if(!q->head) return 0;
	stack s1;
	Node* node{};
	// Create the stack
	for(int index{0}; index < k; index++){
		q->dequeue(node);
		s1.push(node);
	}
	
	// Display the values in the stack
	for(int index{0}; index < k; index++){
		s1.pop(node);
		cout << node->val << " ";
	}
	
	// Displays the rest of the queue
	for(int index = k; index < q->size(); index++){
		q->dequeue(node);
		cout << node->val << " ";
	}
	
	return 1;
}
```
### Question C
Undo operation in software. The most recently made changes is pushed on the stack. When the undo operation is used, the changes is retrieved from the top of the stack.
## Question 3
### Question A
#### Question I
![[Past Year Papers/Year 1/Semester 3/Data Structure and Algorithms/Diagrams/may_2023/merge_sort|450]]
#### Question II
Use merge sort. The best case scenario is when the given array is already sorted. 
### Question B
![[Past Year Papers/Year 1/Semester 3/Data Structure and Algorithms/Diagrams/september_2022/binary_search|500]]

#### Coding 
##### Recursive approach
```cpp
std::string binarySearch(std::string array[], std::string& key, int start, int end){
	int middle{};
	if (start <= end){
		middle = (start + end)/2
		if(array[middle] == key) 
			return array[middle];
		if (array[middle] > key) 
			return binarySearch(array, key, start, middle-1);
		return binarySearch(array, key, middle+1, end);
	}
	return "0";
}
```
##### Iterative approach
```cpp
std::string binarySearch(std::string array[], std::string&key, int start, int end){
	int middle{};
	while(start <= end){
		middle = (start+end)/2;
		if(array[middle] == key) return array[middle];
		if (array[middle] > key) end = middle -1;
		else start = middle+1;
	}
	return "0";
}
```

### Question C

| f(n)                           | Step 1                       | Step 2                      | Derived Big-O     |
| ------------------------------ | ---------------------------- | --------------------------- | ----------------- |
| $8n^5 + 9 n^2$                 | $n^5 + n^2$                  | $n^5$                       | $O(n^5)$          |
| $6n * (log_2\; n)+ log_2 \; n$ | $n * (log_2 \; n) + log_2 n$ | $n\; log_2 \;n + log_2\; n$ | $O(n \;log_2\;n)$ |
| $10 + c ( c$ is a constant)    | 1                            | 1                           | $O(1)$            |

# Section B
## Question 4
### Question I
![[Past Year Papers/Year 1/Semester 3/Data Structure and Algorithms/Diagrams/september_2022/bst|350]]
### Question B
```cpp
void BST::largerThan(BTNode *ptr, int value){
	if(!ptr) return;
	largerThan(BTnode->left, value);
	if (ptr->value > value) std::cout << ptr->value " ";
	largerThan(BTnode->right, value);
}
```
### Question C
#### Question I
Stacks. You save the most recently visited browser on the top of the stack
Graphs. One node can lead to multiple nodes with different weights representing the length.
#### Question II
Graph. A graph can have multiple pathways from a node to another node
## Question 5
### Question B
#### Question I
```cpp
bool iterativeCheckSortedArr(int arr[], int n){
	for(int index = 0; index < n-1; index++){
		if (!(arr[index] < arr[index + 1]))
			return false;
	}
	return true
}
```
#### Question II
```cpp
bool recursiveCheckSortedArr(int arr[]. int n){
	if(n == 1) return true;
	if(!(arr[n-1] > arr[n-2])) return false;
	return recursiveCheckSortedArr(arr, n-1);
}
```