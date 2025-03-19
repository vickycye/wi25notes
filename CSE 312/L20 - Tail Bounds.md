26 February 2025

---
### Quick notes
- Quiz 2 next week in section [up to Central Limit Theorem (maybe joint probability)]
- Midterm 72% median

### To do
- [ ] Watch a video on tail bounds [Markov and Chebyshev]
- [ ] Finish Homework 6
- [ ] Concept check 20

---
## Lecture Notes

### Confidence Intervals
Tells you the probability that your RV fell in a certain range, which is usually close to its expected value. 
$$\mathbb{P}(|X - \mu| > \epsilon) \leq \delta$$
$\mu$ is the population parameter--the expected mean
$X$ is the sample parameter--the sample mean
$\epsilon$ is the distance from the mean
$\delta$ is the part in the tail

A tail bound is the probability of being outside the margin of error, aka in the "tails" of the distribution [such as there is very little probability far from the center].

### Markov's Inequality
>Let $X$ be a RV supported only on non-negative numbers. For any $t > 0$,
>$$\mathbb{P}(X \geq t) = \frac{\mathbb{E}[X]}{t}$$
  For any $k > 0$:
  $$\mathbb{P}(X \geq k \mathbb{E}[X]) \leq \frac{1}{k}$$
  Only works for non-negative distributions, such as binomial or geometric.

![[markov_inequality.png]]
If you increase the tail probability, the expectation goes up, if you decrease the tail probability, then the expectation goes down. 

**Markov bound** is always an upper bound on the probability that a non-negative RV takes on a value as least as large as some positive constant (k). This is a step towards understanding **Chebyshev's inequality** and **Chernoff bounds**

**Example:**
Suppose the average number of ads you see on a website is 25. Give  an upper bound on the probability of seeing a website with 75 or more ads
$\mathbb{P}(X \geq 75) = \frac{25}{75} = \frac{1}{3}$

### Chebyshev's Inequality
>Let $X$ be a RV. For any $t > 0$
>P(|X - E[X]| >= t) <= var(x) / t^2

**Same Example**
$Var(X) = \frac{\frac{5}{6}}{\frac{1}{36}} = 30$
$E[X] = 6$

$P(X \geq 12) \rightarrow P(X - 6 \geq 6) \rightarrow P(|X-6|\geq 6)$

$$P(|X - 6| \geq 6) \leq \frac{30}{36}$$
=> $\frac{5}{6}$

For larger probabilities, Chebyshev's is better. 

**Example**
Now suppose the Var(X) of ads is 16.
Using Chebyshev's inequality, the upper bound is $\frac{16}{25}$



---
Back to: [[CSE 332 A - Class Details]]

#ComputerScience