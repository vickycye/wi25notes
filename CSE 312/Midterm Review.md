19 February 2025

---
### Quick notes
- Evening exam
- Pigeonhole principle on the exam will be more intuitive than Q15 on the midterm review
- "feels like magic" - robbie 2025

### To do
- [ ] Practice Exams

---
## Topics
1. Counting
	- Combinations
	- Permutations
	- Indistinguishable elements
	- Stars and bars
	- Inclusion-exclusion
1. Probability Foundations
	- Events
	- Sample spaces
	- Axioms of probability
	- Expectation
	- Variance
1. Conditional Probability
	- Law of total probability
	- Bayes' Theorem

---
## Notes from Slides
![[counting_techniques.png]]

Mutually exclusive and independent events are different concepts in probability but they do have some relation. Mutually exclusive events cannot occur at the same time, and independent events don't influence each other. 

How to identify pigeonhole questions: Either the first thing you think of to solve the problem or the last.

> Q15 from midterm review section
   We add all the subsets of $a_i$: maximum sum is $n$, minimum sum is 0. 
   There are $2^n$ subsets, but one of them is the empty set. So we have $2^n - 1$ non-empty sets. We are assigning either -1, 0, or 1 to each of the coefficients. We have to identify those values that are near each other. We want $2^n - 2$ pieces of the number line, and each length is $\frac{n}{2^n - 2}$. We have fewer pieces than I have subsets, so there must be one of the pieces that are in the same interval.
   
> For this problem,  we're assuming that $n$ is reasonably large, otherwise the pigeonhole principle won't hold true (or it doesn't make much of a good argument)

[Discrepancy theory - Wikipedia](https://en.wikipedia.org/wiki/Discrepancy_theory)



---

Fun problem to try:
You have 3 cards: One card has both sides red, one card has both sides black, and one card has one side red and one side black. You pick a random card from the 3 and place it on the table. The side facing you is Red. What's the probability that the other side is also red?

You have a 6 sided die which you roll 6 times. What's the probability that you see at least 2 consecutive 6's?


---
Back to: [[CSE 312 A - Class Details]]

#ComputerScience