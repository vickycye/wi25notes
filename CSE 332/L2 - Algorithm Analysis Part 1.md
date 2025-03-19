8 January 2025

---
### Quick notes
- More about generics in section

### To do
- ~~Turn in EX0~~

---
## Lecture Notes

What matters in algorithms?
- Correctness
- Performance: Speed, Memory
	- Time complexity, space complexity

### Analysing Code ("worst case")

Basic operations take <mark style="background: #BBFABBA6;">constant time:</mark>
- Arithmetic
- Assignment
- Access one Java field or array index
- Etc.

Consecutive statements -> Sum of time of each statement, adding everything together
```
b = b + 5         // Two operations
c = b / a         // Two operations
b = c + 100       // Two operations, 6 total operations -> O(1)
```

Loops -> Numbers of iterations $\times$ The time it takes to run the loop's body
``` 
// n = "problem size", operations = ++, <
for (int i = 0; i < n; i++) {        // 4 ops * n times + 2 ops = O(n)
	sum++;
}
```

Conditionals -> Time of condition plus time of slower branch
```
if (j < 5) {                             // Branch 1: 2 ops
	sum++;
} else {
	for (int i = 0; i < n; i++) {        // Branch 2: 4n + 1 op
		sum++;
	}
} // Worst case is branch 2 = O(n)
```

Functional Calls -> The time it takes for the function's body to run
```
public int method() {                    // method runtime is O(m * n)
	for (int i = 0; i < n; i++) {
		for (int j = 0; j < n; j++) {
			// Something happens
		}
	}
}
```

Recursion -> <mark style="background: #ABF7F7A6;">Solve recurrence equation</mark>
[Will cover this more next week(?)]


For LinkedList vs. ArrayList operation runtimes, see more at: [[L12 - LinkedList]] from [[CS 211 - Class Details]]

### Complexity 
- **Worst-case complexity**: max # of steps the algorithm takes on the "most challenging" input of size N
- **Best-case complexity**: minimum # of steps algorithm takes on "easiest" input of size N
- **Average-case complexity**: average # of steps the algorithm takes on random inputs of size N
- **Amortized complexity**: max total # steps algorithm takes on M "most challenging" consecutive inputs of size N, divided by M

More on amortized complexity: [Some Notes on Amortized](https://courses.cs.washington.edu/courses/cse332/23sp/lectures/Amortized.html) [It's called aeh-more-tized]

#### Searching Algorithms in an Array

In class, we covered Linear search, which is O(n), but there is a faster method: Binary search, which takes O(log n) time.

### Ignoring Constant Factors

For binary search and linear search, depending on constant factors, linear search can actually be faster for some numbers of $n$. 
- As seen in a graph, small values of $n$ in linear search is faster than binary search, which evens out over time. 

![[BigOChart.png]]

### Asymptotic Analysis

1. Eliminate low-order terms
2. Eliminate coefficients

$3n^2 + 7$ and $n^2$ have the same asymptotic behavior.

#### Formal Definition of BigO Notation
>$g(n)$ is in $O(f(n))$ iff there exist positive constants $c$ and $n_0$ such that $g(n) \leq c f(n)$ for all $n \geq n_0$. 

Common Big-O Notations
Fastest to slowest:

| O(1)       | constant    |     |
| ---------- | ----------- | --- |
| O(log n)   | logarithmic |     |
| O(n)       | linear      |     |
| O(n log n) | n log n     |     |
| O(n^2)     | quadratic   |     |
| O(n^3)     | cubic       |     |
| O(n^k)     | polynomial  |     |
| O(k^n)     | exponential |     |


---
Back to: [[CSE 332 A - Class Details]]

#ComputerScience 