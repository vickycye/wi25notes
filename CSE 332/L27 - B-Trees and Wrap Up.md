14 March 2025

---
### Quick notes
- Review session on Tuesday
- Kane hall in exam
- Take CSE 351 with Ruth next year
### To do
- [ ] Write thank you email to Ruth

---
## Lecture Notes

This topic has not been covered in this class yet--but was covered in previous quarters. 

### B-Trees
-> dictionary that considers the memory hierarchy

Memory Hierarchy: [Memory Hierarchy Design and its Characteristics - GeeksforGeeks](https://www.geeksforgeeks.org/memory-hierarchy-design-and-its-characteristics/)
![[memory_hierarchy.png]]

- Data from larger storages of memory tend to be harder to access, with the Disk taking up to 8 million instructions to access. We move it up through the hierarchy until we get to the registers and cache which are faster to access.

**Locality**
1. Temporal locality: if an address is referenced, it will tend to be referenced again soon [loop variable, root node of a tree]
2. Spatial locality: if an address is referenced, addresses that are close by will tend to be referenced soon [array that is accessed in order]


Arrays are more likely to take advantage of spatial locality because it's a structure that's very close by [i.e. 4 elements of an array can be part of a disk block]. 
- Every time you say `new` in Java, you're asking for a chunk of memory thats anywhere. 

[aka do not use data structures that have pointers in them]

### B-Trees
This is designed for efficient memory allocation--trying to fill up a disk block as much as possible so the other elements are more efficient to balance. 

Disk access: 8 million instructions
BST worst case runtime is $O(N)$, and there are roughly 10 million disk accesses, very expensive
AVL worst case runtime is $O(\log N)$ and there are roughly 25 disk accesses
B-Tree worst case runtime is $O(\log_M N)$ and there are roughly 3-4 disk accesses

Properties:
- Have an array of sorted children
- We have a search tree with branching factor of $M$. 
- The height of a B tree is $O(\log_{M} N)$
- Binary search to determine which pointer to follow -- $O(\log_2 M)$ 

Worst case runtime of `find`: $O(\log_{2}M \cdot \log_{M} N)$

[How do we rebalance the tree to make sure the search runtime doesn't become linear?]

### B+ Trees
Two types of nodes: interval nodes and leaves
- Each internal node has room for up to M - 1 keys and M children -> no other data; all data at the leaves

- Usually implement in C/C++





---
Back to: [[CSE 332 A - Class Details]]

#ComputerScience