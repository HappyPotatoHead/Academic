---
aliases:
  - September 2023
tags:
  - PYQ
  - DSA
Date: 2024-05-15
Completion: true
obsidianUIMode: preview
---
# Section A
## Question 1
### Question A
*ptr points to cat*
#### Question I
*cat.breed\[5\]*
s
#### Question II

Silver
#### Question III
a
#### Question IV
Error. 
- [!] cat.next is a pointer
### Question B 
**Remember these are not pointers except for head**
Full linked list until *III*
![[complete_linked_list|750]]
#### Question I
![[partial_linked_list|750]]
#### Question II
```c++
item5.next = item1.next;
item1.next = &item5;
```
#### Question III
```cpp
item2.next = &item4;
```
#### Question IV
```c++
item5.next = item2.next;
delete item2;
```
#### Question V
```C++
void print(Node* head){
	Node* current = head;
	while (current){
		cout << current->item << '\n';
		current = current->next;
	}
}
```
## Question 2
### Question A
#### Question I

| Queue                        | Stack                      |
| ---------------------------- | -------------------------- |
| insert from the back         | insert from the top        |
| delete from the front (FIFO) | delete from the top (LIFO) |
#### Question II
![[Past Year Papers/Year 1/Semester 3/Data Structure and Algorithms/Diagrams/september_2023/stack_and_queue|1000]]
#### Question III
![[Past Year Papers/Year 1/Semester 3/Data Structure and Algorithms/Diagrams/september_2023/stack|500]]
### Question B
#### Question I
Binary Search Tree. Since the appointments will be sorted, Binary Search Tree makes searching quick and efficient
#### Question II
Doubly Linked List. When the player meets a ladder, it can jump to different nodes easily
#### Question III
Tree. Tree, like file explorer, has hierarchical properties. A tree can mimic the hierarchy present in file explorer
#### Question IV

| Big-O notation | Binary Search | Hash Table |
| -------------- | ------------- | ---------- |
| Best Case      | O($1$)        | O(1)       |
| Worst Case     | O($log n$)    | O(n)       |

>[!NOTE]- Big-O for Data structures
> **Trees**
> - **Binary Search Tree or Ordinary Tree**
> 	- Best case is $O(log n)$
> 	- Worst case is $O(n)$ 
> 		- It may turn into linked list
> - **AVL trees**
> 	- Since balancing is done, the tree is always in its best shape
> 	- Both best case and worst case is $O(log n)$
> **Linked lists**
> - **Singly linked list and doubly linked list** 
> 	- Search
> 		- Best case is $O(1)$
> 			- You immediately find the value
> 		- Worst case is $O(n)$
> 			- The item is at the end of the list (you don't have a tail pointer)
> 	- Insertion
> 		- Best case is $O(1)$
> 			- Insert at the front of the list or at the back (if you have a tail pointer)
> 		- Worst case is $O(n)$ (No tail pointer)
> 			- Insert at the end of the list
> 				- Have to traverse to the end
> 			- Somewhere in the middle is still $O(n)$
> 	- Delete
> 		- Best case is $O(1)$
> 		- Worst case is $O(n)$
> - **Queue (*singly linked list*)**
> 	- Delete
> 		- Best case is $O(1)$
> 			- Since you delete from the front
> 	- Insertion
> 		- Best case is $O(1)$ (Tail pointer is present)
> 			- You always insert to the back of the list  
> 		- Worse case is $O(n)$ 
> 	- Search
> 		- Best case is $O(1)$
> 			- The first thing you find.
> 		- Worse case is $O(n)$ (No tail pointer)
> 			- At the end of the list (you dont have a tail pointer)
> - **Stack (*singly linked list*)**
> 	- Search 
> 		- Best case is $O(1)$ 
> 			- Since you retrieve from the top
> 		- Worst case is $O(n)$
> 	- Insertion
> 		- Best case and worst case is $O(1)$
> 			- You always insert from the top
> 	- Delete
> 		- Best case and worse case is $O(1)$
> 			- You always delete from the top


>[!TLDR] TLDR
>**Searching** 
>- best case is always O(1) and worst case depends on the data structures/algorithm
>
>**Inserting** 
>- best case is also O(1) if insert at the first node or last if tail pointer exists
>
>**Delete** 
>- best case is also O(1) if you delete the front or end if tail pointer exists 
## Question 3
### Question A
![[Past Year Papers/Year 1/Semester 3/Data Structure and Algorithms/Diagrams/september_2023/merge_sort|500]]
### Question B

| Index | value               |
| ----- | ------------------- |
| 0     | Durian -> Jackfruit |
| 1     | Mango -> Mangosteen |
| 2     | Apple               |
| 3     | Banana              |
| 7     | Grape -> Orange     |
### Question C
**O(1)**
```c++
// Assignment is O(1)
type temp
int n
n = list.size()
```
**O($n^2$)**
```cpp
for(int i = 1; i <= n; i++){ // this is O(1) + O(n)
	if(!list.get(i,temp)) // This is O(n) + O(1)

// O(n) + 1 = O(n)
// O(n) inside O(n) = O(n) x O(n)
```
Total = $3 \times O(1)$ + $O(n^2)$ = $O(n^2)$

# Section B
## Question 4
### Question A
#### Question I...
![[Past Year Papers/Year 1/Semester 3/Data Structure and Algorithms/Diagrams/september_2023/bst|500]]

### Question B
```cpp
void BST::printLevelNodes2(BTNode *cur, int cnt, int level){
	if(!cur || level > cnt) return;
	if (level == 1)
		cout << "Level " << level << "nodes: \n";
		cout << cur->value;
	else {
		cout << "Level " << level << "nodes: \n";
		cout << cur->value;
		return; 
	}
	printLeveLNodes2(cur->left, cnt, level+1);
	printLevelNodes2(cur->right,cnt, level+1); 

}
```

```cpp
int level{1};
int height = heightofTree(root);
cout << height << '\n';

for(int index{1}; index <= height; index++){
	cout << "Level " << index << " nodes: \n";
	levelOrder2(root, index, level);
	cout << "\n";
}
        
void levelOrder2(TreeNode* root, int height, int level){
	if (!root) return;
	if (level == height)
		cout << root->val << ' ';
	else{
		levelOrder2(root->left, height, level+1);
		levelOrder2(root->right, height, level+1);
        }
    }
```
### Question C
#### Question I 
Yes
#### Question II
No. Since, 100 is bigger than 89, it should traverse to the right side of 89 which is larger than 89. 
## Question 5
### Question C
```cpp
int addArray(int arr[], int n ){
	if (n == 0) return 0;
	return addArray[n-1] + addArray(arr, n -1);	
}
```