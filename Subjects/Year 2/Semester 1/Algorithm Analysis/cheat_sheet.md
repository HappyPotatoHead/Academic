---
aliases: 
tags:
  - Notes
  - DSA
Date: 2023-09-18
Completion: true
obsidianUIMode: preview
---
# Content

## Trees

1. [[#Related to the height of trees]]
2. [[#Printing level by level nodes]]
3. [[#Displaying all possible path]]
4. [[#Inverting Tree]]

## Linked List

1. [[#Floyd's algorithm]]
2. [[#Merging linked list]]
3. [[#Traversing matrix]]
## Sorting and Search

1. [[#Binary Search]]
2. [[#Quick Sort]]

---

## Trees

### Related to the height of trees

#### Checking height of the tree

^fda350
```cpp
int height(BTNode* root){
	if(!(root)) return 0;
	int left{ height(root->left) };
	int right{ height(root->right) };
	return max(left+1, right+1);
	/* 
	if(left > right) return left+1;
	else return right+1;
	*/
}
```

#### Checking if the tree is balanced

- Modify the height function

```cpp
int height(BTNode* root, bool& isBalanced){
	if(!root) return 0;
	int left{ height(root->left) };
	int right{ height(root->right) };
	if(abs(left-right) > 1) 
		isBalanced = 0;
	return max(left+1, right+1);
}
```

### Printing level by level nodes

#### With Queue (Basic)

```cpp
bool BSF(BTNode* root){
	if(!root) return;
	Queue q;
	q.enqueue(root);
	type* node{nullptr};
	while(!q.empty()){
		q.dequeue(node);
		cout << node->value << " ";
		if(node->left) q.enqueue(node->left);
		if(node->right) q.enqueue(node->right);
	}
	return 1;
}
```

#### With Queue (modified)

- This creates a 2d queue
- The same concept applies to lists 
	- List is probably more probable for FE

```cpp
bool BSF(BTNode* root){
	if(!root) return 0;
	Queue<int> q;
	Queue<Queue> q2;
	q.enqueue(root);
	type* Node{ nullptr };
	while(!q.empty()){
		Queue<node> minor;
		for(int index{0}; index< minor.size(); index++){
			q.dequeue(node);
			minor.enqueue(node);
			if(node->left)q.enqueue(node->left);
			if(node->right)q.enqueue(node->right);
		}
		q2.enqueue(minor);
	}
	return 1;
}
```

#### Using [[#^fda350|Height function]]

**This is one of the ways to do it**

*Starting point*

```cpp
bool BSF1(BTNode* root){
	if(!root) return 0;
	int T_height{ height(root) };
	for(int index{0}; index < T_height; index++)
		BSF2(BTNode* root, index);
	return 1;
}
```


*Printing starts here*

```cpp
void BSF2(BTNode* root, index){
	if(!root) return;
	if(index == 0)
		std::cout << root->value;
	BSF2(root->left, index-1);
	BSF2(root->right, index-1);
}
```

### Displaying all possible path

#### Using Lists

- *int pathindex{0}*
- *int solutionindex{0}*

```cpp
void paths(BTNode* root, int path[], string solution[][], int pathindex, int solutionindex){
	if(!root) return;
	path[index] = root->value;
	index++;
	if(!(root->left) && !(root->right)){
		solution[solutionindex] = path;
		solutionindex++;
	}
	else{
		paths(root->left, path, solution, pathindex, solutionindex);
		paths(root->right, path, solution, pathindex, solutionindex);
	}
	path[index] = -1;
}
```

#### Using vectors

```cpp
void paths(BTNode* root, vector<int>& path[], vector<string>& solution){
	if(!root) return;
	path.push_back(root->val);
	if(!root->left && !root->right){
		string temp{};
		for(int index{0}; index < path.size();index++){
			temp += string(path[index]);
			if(index < path.size() -1)
				temp+="->";
		}
		solution.push_back(temp);
	}
	else{
		paths(root->left, path, solution);
		paths(root->right, path, solution);
	}
	path.pop_back();
}
```

#### Just printing

- *length = 0*

```cpp
void paths(BTNode* root, int path[], int length){
	if(!root) return;
	path[length] = root->value;
	length++;
	if(!root->left && !root->right){
		for(int index{0}; index < length; index++){
			cout << path[index] << " ";
		}
		cout << "\n";
	}
	else{
		paths(root->left, path, length);
		paths(root->right, path, length);
	}
}
```

### Inverting Tree

```cpp
void invertTree(BTNode* root){
	if(!root) return;
	invertTree(root->left);
	invertTree(root->right);
	BTNode* tempLeft{root->left};
	root->left = root->right;
	root->right = tempLeft;
}
```

## Linked List

### Floyd's algorithm

#### Check if a loop exists

```cpp
bool HareandTortoise(Node* head){
	if(!head) return 0;
	Node* tortoise{head};
	Node* hare{head->next};
	while(tortoise && hare->next){
		if(tortoise == hare)
			return 1;
		(tortoise->next) ? tortoise = tortoise->next; tortoise = nullptr;
		(hare->next->next) ? hare = hare->next->next; hare=nullptr;
	}	 
	return 0;
}
```

#### Check the starting point of the loop

```cpp
Node* HareandTortoise(Node* head){
	if(!head) return nullptr;
	Node* tortoise{head};
	Node* hare(head->next);
	while(tortoise && hare->next){
		if(tortoise == hare){
			tortoise = head;
			while(tortoise != hare){
				tortoise = tortoise -> next;
				hare = hare->next;
			}
			return tortoise;
		}
		(tortoise->next) ? tortoise=tortoise->next: tortoise=nullptr;
		(hare->next->next) ? hare = hare->next->next: hare=nullptr;
	}
	return nullptr;
}
```

### Merging linked list

```cpp
bool mergeList(List list1, int size1, List list2, int size2, List *list3){
	if(size1 == 0 || size2 == 0|| list3->head) return 0;
	Node* head1 = &list1.head;
	Node* head2 = &list2.head;
	int index{1};
	while(head1 && head2){
		if(head1->val < head2 -> val){
			list3->insert(index, head1->val);
			head1 = head1->next;
		}else{ 
			list3->insert(index, head2->val);
			head2 = head2->next;
		}
		index++;
	}
	// these two are for when one list is shorter than the other
	while(head1){
		list3->insert(index, head1->val);
		head1= head1->next;
		index++;
	}
	while(head2){
		list3->insert(index, head2->val);
		head2= head2->next;
		index++;
	}
	return 1;
}
```

### Traversing matrix

#### Starting from the top left corner

**Idk why I did this**

- *Assuming it's sorted*
- *Assuming it's a doubly linked list*

```cpp
bool TraverseMatrix(Node* head, int key){
	if(!head) return 0;
	while(head->next){
		head = head ->next;
	}
	while(head){
		if(head->val == key) return 1;
		else if(head->val < key)
			(head->bottom) ? head = head->bottom : head = nullptr;
		if(head->val > key)
			(head->prev) ? head = head->prev: head = nullptr;
	}
	return 0;
}
```

#### Brute Force

- *Assume it is a doubly linked list*

```cpp
bool Traverse(Node* head, int key, int row, int column){
	for(int index1{0}; index1 < row; index1++){
		for(int index2{0}; index2 < column; index2++){
			if(head->val == key) return 1;
			if(index1%2 == 0) 
				(head->next) ? head = head->next: head = head;
			else 
				(head->prev)? head = head->prev: head = head;
		}
		head = head->bottom;
	}
}
```

### Reversing Linked list

#### Reversing the middle of the list

```cpp
bool reverseBetween(Node* head, int left, int right){
	if(!head) return 0;
	Node* current{head};
	Node* start{null};
	// Stores the node before the starting point
	for(int index{0}; index < left-1; index){
		start = current;
		current = current->next;
	}
	Node* previous{nullptr};
	// Begin reversing
	for(int index{0}; index < (left - right + 1); j++){
		Node* tempNext{current->next};
		current->next = previous;
		previous = current;
		current = tempNet;
	}
	start->next->next = current;
	start->next = previous
	return 1;
}
```

#### Reversing the entire list

```cpp
bool reverse(Node* head){
	if(!head) return 0;
	Node* previous{nullptr};
	Node* current{head};
	while(current){
		Node* tempNext = current->next;
		current->next = previous;
		previous = current;
		current = current->next;
	}
	return 1;
}
```

## Search and Sort

### Binary Search

#### Iterative approach

```cpp
bool Binary(int array[], int key, int start, int end){
	int middle{};
	while(start <= end){
		middle = (start + end) /2;
		if(array[middle] == key)
			return 1;
		else if(array[middle] > key)
			end = mid--;
		else 
			start = mid++;
	} return 0;
}
```

#### Recursive approach

```cpp
bool Binary(int array[], int key, int start, int end){
	int middle{};
	if(start <= end){
		middle = (start + end) /2;
		if(array[middle] == key)
			return 1;
		if(array[middle] > key)
			return Binary(array, key, start, mid-1);
		return Binary(array, key, mid+1, end);
	}
	return 0;
}
```

### Quick sort

```cpp
void Quicksort(int array[], int size){
	int k{};
	int index{};
	int middle{size/2};
	swap(array[0], array[middle]);
	for(k =1; k < size; k++){
		if(array[0] > array[k]){
			index++;
			swap(array[index], array[k]);
		}
	}
	swap(array[0], array[index]);
}
```
