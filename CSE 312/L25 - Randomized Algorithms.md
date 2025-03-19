10 March 2025

---
### Quick notes
- More of this on Wednesday

### To do
- [ ] Homework 8
- [ ] Finals prep -- on webpage
- [x] Concept check 25 ✅ 2025-03-11

---
## Lecture Notes

- MLE slightly underestimates the true variance--you just have to multiply by $\frac{n}{n - 1}$

Maximum a posteriori estimation: picking the maximum value of $\mathbb{P}(\theta | E)$ starting from a known prior over possible values of $\theta$. 

### Randomized Algorithms
An algorithm that uses randomness in the computation. We hope these will be faster than if we didn't use randomness. 

#### Monte Carlo Algorithm
- Usually tells you the right answer, sometimes the wrong one.
- The Big-O time complexity of a Monte-Carlo algorithm will not be affected by the random choices made.
- If a problem can have a Monte-Carlo algorithm be applied to it, then a non-Monte-Carlo algorithm can also be applied to it.

#### Las Vegas Algorithm
- Always tells you the right answer
- Takes varying amount of time
- Pivot closer to the middle works better [But the LV algorithm is choosing any pivot uniformly at random]

Theorem
>With probability of at least $1 - \frac{1}{n}$, Quicksort runs in time $O(n \cdot \log n)$




---
Back to: [[CSE 312 A - Class Details]]

#ComputerScience 