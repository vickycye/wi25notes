13 January 2025

---
### Quick notes
- Finish up intro to asymptotic analysis
- learning a new ADT - priority queues
- there's a form to fill out for extensions
- EX02 will be related to priority queues-- implementation exercise
- In this class, the most common thing we're gonna do is give an O or $\theta$ bound to the worst-case running time of an algorithm
- STAT 391: probability 1 (STAT 394) -> STAT 391

### To do
- EX01 on gradescope (it says submitted but i only did two questions)
- Read textbook chapter 6

---
## Lecture Notes

- Normally, people just use $\Omega()$ for runtime analysis with a tight-bound meaning

### Summary
Analysis can be about:
- The problem or the algorithm (usually algo)
- Time or space 
- Best-, worst-, average-case (usually worst)
- Upper-, lower-, tight-bound (usually upper or tight)

|         | O   | $\Omega$ | $\theta$ |
| ------- | --- | -------- | -------- |
| Best    |     |          |          |
| Worst   |     |          | yes      |
| Average |     |          |          |

### Priority Queue ADT

>Queue vs Priority Queue: First come, first serve (like lining up in the bathroom) vs. assigning priorities based on each individual's need (like in the ER).

A **priority-queue** holds <mark style="background: #FFF3A3A6;">compare-able data</mark>:
- Each item has a priority
- Min-heap is an implementation
- Main operations: `insert` or `deleteMin`
- The item with the least number is the one with the greatest priority. (priority 1 is more important than priority 45). [can also do maximum priority]
- If there is a tie, we can resolve them arbitrarily [pick any one and remove]

|                       | insert                                                                                                              | deleteMin                        |
| --------------------- | ------------------------------------------------------------------------------------------------------------------- | -------------------------------- |
| Unsorted Array        | O(1)                                                                                                                | O(n)                             |
| Unsorted Linked-List  | O(1) [insert at front]                                                                                              | O(n)                             |
| Sorted Circular Array | O(n) [have to shift all elements left]                                                                              | O(1) [delete first node]         |
| Sorted Linked-List    | O(n) [have to maintain sorted]                                                                                      | O(1) [just remove the first one] |
| Binary Search Tree    | O(n) [<mark style="background: #FFF3A3A6;">could be a "linked-list", since theres no guarantee its balanced</mark>] | O(n) [absolute worst-case]       |

- We will use `int`s as both data and priority

### Applications of Priority Queues
1. Run multiple programs in the OS
2. Triage
3. Select print jobs in order of decreasing length
4. Forward network packets in order of urgency
5. Select most frequent symbols for data compression
6. Sorting
7. Greedy algos
8. Discrete event simulation:
	1. Pending events

Current bad data structures with bad linear runtime: 

![[ds_and_runtime.png]]

### Trees
`degree()` is how many children a node has
`branchingFactor()` is least number of branches to most.

Types of trees:

| Binary Tree   | Every node has $\leq 2$ children                                                       |
| ------------- | ------------------------------------------------------------------------------------- |
| n-ary tree    | Every node has $\leq n$ childr                                                         |
| Perfect tree  | Every row is completely f                                                              |
| Complete tr All rows except the bottom are full, and the bottom row is filled from left to right. ll,  |

### Binary Min-Heap
- Is a complete binary tree
- Heap order property: Every non-root node has a priority value larger than the priority value of its parent.
- Minimum priority is at the root [requires O(log n)] to remove, since bubbling down is necessary
- Height of a heap with n items is log n, and when you add, you add at the next leaf node spot, then bubble up. [O (log n)]

[next lecture: learning how to bubble down and bubble up]

---
Back to: [[CSE 332 A - Class Details]]

#ComputerScience 