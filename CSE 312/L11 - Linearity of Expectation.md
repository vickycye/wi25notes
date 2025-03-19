31 January 2025

---
### Quick notes
- 

### To do
- [ ] Concept check 11
- [ ] Homework 4 due wednesday
- [ ] intro to machine learning textbook and youtube videos
- [ ] Search up applications of linearity of expectation

---
## Lecture Notes

### Linearity of Expectation
>For any two random variables, the expectation of the sum of them is equivalent to the sum of their expectations.
>$\mathbb{E}[X + Y] = \mathbb{E}[X] + \mathbb{E}[Y]$

Note: X and Y do not have to be independent

[Search up applications of linearity of expectation]
- Linearity of expectation is kind of like linear combinations [[L2 - Lines and Linear Equations]], where they can be distributed outside of the expectation and still have the same value as if they were inside. 

**Example**
If we flip a coin twice, what is the expected number of heads that come up

$$p_f(F) = \begin{cases} 
		\frac{1}{4}	& f = 0 \\
		\frac{1}{2}	& f = 1 \\
		\frac{1}{4}	& f = 2 \\
		0	& \text{otherwise}
\end{cases}$$

Now what if the probability of flipping a head was $p$ and that we wanted to find the total number of heads flipped when we flip the coin $n$ times?

An original guess would be $np$, because we're flipping $n$ times with a chance of $p$ for a head. 
$$\mathbb{E}(X) = \sum_{k = 0}^{n} k \cdot \mathbb{P}(Y = k) = \sum_{k = 0}^{n} k \cdot {n \choose k} p^k (1 - p)^{n - k}$$
if you simplify that -> you get $np$. Crazy!

### Indicator Random Variable
[web.stanford.edu/class/archive/cs/cs161/cs161.1236/Resources/prob.pdf](https://web.stanford.edu/class/archive/cs/cs161/cs161.1236/Resources/prob.pdf)

- The expectation of an indicator random variable is just the probability of an event occurring.  

**Example**
Let $X$ be the number of heads. What indicators can we define? What 'booleans' have enough information to combine and solve the problem?

E[X_i] for the indicator variable, it's either 1 if its heads or 0 otherwise (tails). E[X_i] = 1 * p + 0 * (1 - p) = p


**Eaxmple**
In a class of m students, one average how many pairs of people have the same birthday?

Let X be the numebr of pairs that have the same birthday
E[X_m] -> 1 for same birthday, 0 for otherwise for each pair












---
Back to: [[CSE 312 A - Class Details]]

#ComputerScience