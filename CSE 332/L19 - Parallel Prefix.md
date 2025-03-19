24 February 2025

---
### Quick notes
- Read textbook on parallelizing quicksort

### To do
- [ ] EX08

---
## Lecture Notes
The `fork-join` framework looks like a tree on top of an upside-down tree.

**Amdahl's Law**
$T_{1} = S + (1 - S) = 1$
- $T_1$ represents the execution time of a task on a single processor without parallelisation
- S is the fraction that has to be run sequentially
- (1 - S) is the fraction that can be run in parallel

If we get $P$ number of processors and had perfect linear speedup, we have $T_{1} = S + \frac{S - 1}{P}$
[more processors means that part goes down and down]

A parallelizing compiler automatically transforms sequential code into parallel code if the machine has multi-core processors or distributed computing environments.

**Perfect linear processing** is parallelizing a program that is exactly proportional to the number of processors used [ideal scenario].

### Work and Span and Reduction
**Work** is the total number of operations required to complete a computation if executed sequentially on a single processor.

**Span** is the longest sequence of dependent operations that must be executed sequentially, even with infinite processors

**Reduction** refers to the process of combining multiple values into a single result, which in our parallelism case, would be the tree approach.

### Prefix Sum
In a typical prefix sum problem, since the next value is dependent on the previous value, we can't really parallelise it: The work is $O(n)$ and the span is $O(n)$ [because its dependent on the entire array].

Another algorithm which takes the sum of the first half of the array, then the first half of the latter half, and etc. has Work: $O(n)$ and span $O(\log n)$. 

### Two-pass prefix-sum algorithm
- Each pass has $O(n)$ work and $O(\log n)$ span. -> In total we also have the same work and span
- First pass builds a tree bottom-up: the "up" pass [in prefix sum we calculate the sum of each individual elements that are paired up, all the way up to the root, which holds the entire sum of the array]
- Second pass traverses the tree top-down: the "down" pass. [in prefix sum we calculate according to each node's fromLeft and sum and we get the final prefix sum array]
	- The left child is calculated by the parent's `fromLeft` field
	- Right child is calculated from sibling's `sum` and parent's `fromLeft`


This dude made it: [Richard Ladner, Professor Emeritus - Paul G. Allen School of Computer Science & Engineering](https://www.cs.washington.edu/people/faculty/ladner-richard/)
##### Generalized
- We can calculate the minimum, maximum, of all the elements to the left of i

### Pack (like filter)
Parallel pack = parallel map + parallel prefix + parallel map

1. We have a parallel map to compute a bit-vector for true elements: [0 for false, 1 for true]
2. We have a parallel-prefix sum on the bit vector
3. And we have another parallel map that produces the output, so we maintain order of the final elements that satisfies the original requirements.

```java
output = new array of size bitsum[n - 1]
FORALL(i = 0; i < input.length; i++) {
	if (bits[i] == 1) {
		// goes in the output array
		output[bitsum[i] - 1] = input[i]
	}
}
```

- The first two steps of parallel map and prefix sum can be combined into one pass

[parallelized packs will help us parallelize quicksort] IN THE READING!!!


---
Back to: [[CSE 332 A - Class Details]]

#ComputerScience