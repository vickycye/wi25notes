7 February 2025

---
### Quick notes
- 

### To do
- [x] 23sp midterm ✅ 2025-02-06
- [x] 23sp midterm - review solutions ✅ 2025-02-06
- [x] 23wi midterm ✅ 2025-02-06
- [x] 23wi midterm - review solutions ✅ 2025-02-06
- [ ] Print out yesterday's section worksheet for both classes
- [ ] 


---
## Ed Discussion Questions

#### What are D-Heaps referring to?
**Question:** Above

**TA response:** That’s referring to heaps with arbitrary branching factor, as opposed to just two, like 3-heaps, 4-heaps, etc. The math and mechanics are nearly identical to that of binary (i.e. 2-) heaps.

**My interpretation**:
[d-ary heap - Wikipedia](https://en.wikipedia.org/wiki/D-ary_heap)
D-Heaps are just heaps where each node has `d` children. They still hold the same property as heaps. Complete tree + nodes either greater than or equal to (max heap) or less than equal to (min heap) their children. 

#### Min/Max Height for AVL Tree Calculation
**Question:** Q6b. I'm wondering if there's a better way to do this exercise other than drawing out the scenarios and counting how many nodes to get to the next maximum/minimum. Is there a formula we can use to find the required amount of nodes for a given maximum/minimum height? if so what is the intuition behind it.

**TA Response:** Hi, I recommend looking at [this slides](https://courses.cs.washington.edu/courses/cse332/25wi/lectures/cse332-25wi-lec08-AVL-A-day2.html) from the lecture. From slide 11, it talks about how we determine the minimum number of nodes of an AVL tree of height h. It doesn't give you a formula to solve for all the questions directly, but will help you gain the intuition behind it. Also, I think it always help to draw out the tree to find/verify your answer.

**My interpretation:**
I still think it's good to draw out the tree using the method that Henouk was doing in class.




---
## Important Things to Remember

| Recurrence Relation                 | Runtime        |
| ----------------------------------- | -------------- |
| $T(n - 1) + c, T(1) = a$            | $O(n)$         |
| $T(n - 1) + nc, T(1) = a$           | $O(n^2)$       |
| $T(\frac{n}{2}) + c, T(1) = a$      | $O(\log_2 n)$  |
| $T(\frac{n}{2}) + nc, T(1) = a$     | $O(n)$         |
| $kT(\frac{n}{k}) + c, T(1) = a$     | $O(n)$         |
| $kT(\frac{n}{k}) + nc, T(1) = a$    | $O(n \log n)$  |
| $T(n - 1) + T(n - 2) + c, T(1) = a$ | $O(2^n)$       |
| $T(n - 1) + n^k c, T(1) = a$        | $O(n^{k + 1})$ |


##### AVL Trees
- The left, right cases are determined from the problem node [it would be nice to draw out the balanced structure and then figure out which one is the problem node, then see rotations from there]


---
## Practice Exams

| Exam | Score          | Topics need to improve                                                       |
| ---- | -------------- | ---------------------------------------------------------------------------- |
| 23sp | 50/75 ~ 66.67% | Code analysis, Big-O, Recurrence, heaps, runtime                             |
| 23wi | 52/77 ~ 67.53% | Robbie's exam, we didn't learn 3 questions wtf -> solve recurrence           |
| 22su | 68/82 ~ 82.93% | Robbie's exam, code analysis and Big-O notation                              |
| 19wi | 79/87 ~ 90.80% | one problem completely didn't know, think of best cases, $O, \Theta, \Omega$ |
|      |                |                                                                              |





---

**NOT-Covered List:** [but you can look into them for fun]
- B-Trees
- Inductive Proofs
- 


---
Back to: [class details]

Tag