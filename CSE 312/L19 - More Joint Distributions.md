24 February 2025

---
### Quick notes
- TA lecture on wednesday
- Review extra slides

### To do
- [ ] Finish homework 6
- [ ] Concept check 19

---
## Lecture Notes

- If we want to find a conditional probability for a joint distribution we can use the formula $P(A | B) = \frac{P(A \cap B)}{P(B)}$
- The condition looks like $p_{U | V} (\text{value of U} | \text{value of V})$

**In-class exercise**
$p_{V | U}(2 | 1) = \frac{2}{16} / \frac{7}{16} = \frac{2}{7}$
$p_{U | V}(1 | 2) = \frac{2}{16} / \frac{3}{16} = \frac{2}{3}$
$p_{U | V}(4 | 1) = 0 / \frac{1}{16} = 0$

##### The continuous version
- Everything is still a density function, not a mass function [joint density, marginal density, conditional density]
- Expectations, conditional expectations integrate the density function

For density functions, it's possible for the denominator to be 0 because the density might not be 0 if we're calculating conditional probabilities. For example: $f_{X | Y}(x | y) = \frac{f_{X, Y}(x, y)}{f_{Y}(y)}$, the marginal density can still be 0. If the density is 0, though, the conditional density is undefined there. 

<span style="color:rgb(255, 192, 0)">U</span><span style="color:rgb(255, 192, 0)">se density to get conditional density !</span>!

In discrete, X, Y are independent if you can multiply the marginal pmf together to get the joint pmf. 

In continuous, X, Y are independent if you can multiply the marginal density function together to get the joint density function.

If X, Y are independent, then the joint support of X, Y must be $\Omega_{X} \times \Omega_{Y}$. [The support is the cartesian product of the independent supports]. [Check the support first and then try to validate the independence by looking at the density functions]

#### Expectations of Continuous Joint Functions
>$$\text{replace with continuous version}$$

#### Conditional Expectation
>$$\text{replace with continuous version}$$

#### Law of Total Probability
> $$\text{replace with continuous version}$$

### Covariance
$$Cov(X, Y) = \mathbb{E}[(X - \mathbb{E}[X])(Y - \mathbb{E}[Y])] = \mathbb{E}[XY] - \mathbb{E}[X] \mathbb{E}[Y]$$
Positive covariance: they vary in the same direction -> positive correlation coefficient
- If $X > \mathbb{E}[X]$, $X - \mathbb{E}[X] =$ a positive result, $Y > \mathbb{E}[Y]$, $Y - \mathbb{E}[Y] =$ a positive result
- If $X < \mathbb{E}[X]$, $X - \mathbb{E}[X] =$ a negative result, $Y < \mathbb{E}[Y]$, $Y - \mathbb{E}[Y] =$ a negative result [double negative = positive]
Negative covariance: they vary in opposite directions -> negative correlation coefficient
 - If $X > \mathbb{E}[X]$, $X - \mathbb{E}[X] =$ a positive result, $Y < \mathbb{E}[Y]$, $Y - \mathbb{E}[Y] =$ a negative result
- If $X < \mathbb{E}[X]$, $X - \mathbb{E}[X] =$ a negative result, $Y > \mathbb{E}[Y]$, $Y - \mathbb{E}[Y] =$ a positive result 

![[covariance_graph.png]]

If $X$ and $Y$ are independent, <span style="color:rgb(255, 192, 0)">covariance is</span> <span style="color:rgb(255, 0, 0)">ALWAYS</span> <span style="color:rgb(255, 192, 0)">0.</span>

If $X$ and $Y$ are dependent, $$Var(X + Y) = Var(X) + Var(Y) + 2 \cdot Cov(X, Y)$$
In general, $Cov(X, -Y) = -Cov(X, Y)$

If W is independent of X, then X is independent of W.

>Covariance is an un-normalized number. Correlation coefficient is calculated with $\frac{Cov(X, Y)}{\sqrt{ Var(X)Var(Y) }}$
> It directly measures only "linear" relationships; if $Y$ depends on $X^2$, then covariance might not be as high as you expect.

### Concept Check

Suppose that we toss a fair coin independently $X$ times, where $X$ is a Poisson random variable with parameter 6. Let $Y$ be the resulting number of heads.

> Question 2.1: What is $\mathbb{E}[Y | X = 10]$?

We can just use a normal binomial distribution, but we can also use the joint distribution approach: $\mathbb{E}[Y] = \mathbb{E}[\mathbb{E}[Y | X]]$

We have $\mathbb{E}[Y | X = x] = x \cdot 0.5$, so we have $\mathbb{E}[Y] = \mathbb{E}[X \cdot 0.5] = 3$

$\mathbb{E}[Y | X = 10] = 10 \times 0.5 = 5$ [which follows the result from the expectation of a binomial distribution with X - Binomial(10, 0.5)]

> Question 2.2: In general, what is $\mathbb{E}[Y | X = k]$?

$\frac{k}{2}$ because that's what we calculated earlier in Q2.1. 

> Question 2.3: What's $$\mathbb{E}[Y] = \sum_{k = 0}^{\infty} \mathbb{E}[Y | X = x] \cdot \mathbb{P}(X = x) = \sum_{k = 0}^{\infty} \frac{k}{2} \cdot \mathbb{P}(X = x)$$

Since $\mathbb{E}[X] = 6$ because $X \sim \text{Poisson}(6)$, we have $$\frac{1}{2} \cdot \sum_{k = 0}^{\infty} k \cdot \mathbb{P}(X = x)$$ which is $$\frac{1}{2} \cdot \mathbb{E}[X]$$ -> $\frac{1}{2} \times 6 = 3$


---
Back to: [[CSE 332 A - Class Details]]

#ComputerScience