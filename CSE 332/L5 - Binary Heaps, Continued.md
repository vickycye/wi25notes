15 January 2025

---
### Quick notes
- Section tomorrow will be talking about Big O proofs
- to analyze the runtime of a tree, you have to understand the relationships between the height, nodes, and leaves.
- in this class we use "percolate" instead of bubble
- Implementation project is on min heaps
- reminder: when percolating down, choose the smaller child node

### To do
- [ ] Finish EX01 by Friday
- [x] Write down pseudocode from slide deck ✅ 2025-01-15
- [x] Transfer handout notes to obsidian ✅ 2025-01-16
- [ ] Review last slide of lecture
- [ ] Read Weiss textbook

---
## Lecture Notes

Review on binary tree, n-ary tree, prefect tree, complete tree. 

- tree height `h` -> `2^h` leaves
- number of nodes => $N = \sum_{i = 0}^{h} 2^i = 2^{h + 1} - 1$

### Binary Min-Heaps
More information in the bottom of: [[L4 - Priority Queues]]
1. has to have a complete tree structure
2. root node and parent nodes have to be bigger than the children nodes

Heap operations:
- findMin: O(1) -- look at root, `return root.data`
- deleteMin: O(log n) -- remove from top, swap with right most leaf, percolate down if needed
- insert(val): O(log n) -- add to the right most leaf area, percolate up

Where children nodes are related to parents:
- left child: $2 \cdot i$
- right child: $2 \cdot i + 1$
- parent (from child): $i / 2$

<mark style="background: #FF5582A6;">!! the pseudocodes use int, but in real use, you will have data nodes with priorities !!</mark>
Pseudocode insert
```
void insert(int val) {
	if (size == arr.length - 1)
		resize()
	size++;
	i = percolateUp(size, val);
	arr[i] = val;
}
```

Pseudocode percolate up
```
int percolateUp(int hold, int val) {
	while (hold > 1 && val < arr[hold / 2]) {
		arr[hole] = arr[hole / 2]
		hole = hole / 2;
	}
	return hole;
}
```

Pseudocode deleteMin() [remember during the project its index 0]
```
int deleteMin() {
	if (isEmpty()) throw error
	ans = arr[1];
	hole = percolateDown(1, arr[size]);
	arr[hole] = arr[size];
	size--;
	return ans;
}
```

Pseudocode percolate down
```
int percolateDown(int hole, int val) {
	while (2*hole <= size) {
		left = 2 * hole
		right = left + 1;
		if (arr[left] < arr[right] || right > size) 
			target = left;
		else
			target = right;
		if (arr[target] < val) {
			arr[hole] = arr[target];
			hole = target;
		} else {
			break;
		}
	}
	return hole;
}
```

#### Other heap operations
- `decreaseKey` given pointer to object in pq, lower its priority value by $p$. -- $\Theta(log N)$
- `increaseKey` given pointer to object in pq, increase its priority value by $p$. -- $\Theta (log N)$
- `remove` given pointer to object in priority queue, remove it from the queue
	- `decreaseKey` with $p = \infty$, then `deleteMin`


### buildHeap() function
```
void buildHeap() {
	for (i = size / 2; i > 0; i--) {
		val = arr[i]
		hole = percolatedown(i, val);
		arr[hole] = val
	}
}
```

- `buildHeap()` is ==O(n) where n is the size of the tree== 
	- Half of the nodes don't need to percolate down, since theyre the leaves with no chidlren
	- In the top $N/2$ nodes, 

- $size / 2$ total loop iterations is O(n) 
- 1/2 the loop iterations percolate at most 1 step
- 1/4 the loop iterations percolate at most 2 steps
- 1/8 of the loop iterations percolate at most 3 steps... etc.
- ((1/2 + 2/4 + 3/8 + ... )) = 2 [page 4 of weiss]

There are at most $2(size / 2)$ total percolate steps: O(n)





In the homework, we're gonna be indexing starting at 0: [Array Representation Of Binary Heap - GeeksforGeeks](https://www.geeksforgeeks.org/array-representation-of-binary-heap/)

---
Back to: [[CSE 332 A - Class Details]]

#ComputerScience 