17 January 2025

---
### Quick notes
- good recursive calls call on something that is smaller
- Formulas provided in exams (log, math)

### To do
- [ ] EX02 programming exercise - heaps

---
## Lecture Notes

### Worst-case Analysis for Recursive Searching Algorithms

Binary search worst case scenario: O (log n) [because it keeps dividing by 2]
- We want a "recurrence" that represents the running time of the recursive code

> Example given in class

**This is the math behind the logic of log (n) runtime!!!!**

$T(n) = 9 + T(\frac{n}{2})$  
1. Count the number of operations in each line
2. Look at the recursive calls, for binary search its $T(\frac{n}{2})$
3. ...
4. Back to this: simplify: $T(n) = 1 + T({\frac{n}{2}})$  
5. $T(n) = 1 + 1 + T({\frac{n}{4}})$  
6. $T(n) = 1 + 1 + 1 + T({\frac{n}{8}})$  
7. Repeat it $i$ times so it becomes $\frac{n}{2^i} = 1$ -> $log_2(2^i) = log_2(n)$ -> $i = log_2(n)$
8. So, $T(n) = \sum_{i = 1}^{log_2(n)} 1 = log_2(n)$
9. Therefore the strict bound runtime is $\theta (\log n)$


Overall structure of recursion:
- <span style="color:rgb(255, 0, 0)">Do some non recursive work</span>
- <span style="color:rgb(50, 50, 255)">Do one or more recursive calls on some portion of your input</span>
- <span style="color:rgb(255, 0, 0)">Do some more non recursive work</span>
- Reach a base case

Running Time: $T(n) = T(p_1) + T(p_2) + \cdots + T(p_x) + f(n)$
- The time it takes to run the algorithm on an input of size $n$ is:
- <span style="color:rgb(50,50, 255)">The sum of how long it takes to run the same algorithm on each smaller input.</span>
- <span style="color:rgb(255, 0, 0)">Plus the total amount of non recursive work done at that step</span> -- $f(n)$

Usually: $T(n) = a \cdot T(\frac{n}{b}) + f(n)$  -> aka divide and conquer
	    $T(n) = T(n - c) + f(n)$ -> aka chip and conquer


---
Back to: [[CSE 332 A - Class Details]]

#ComputerScience