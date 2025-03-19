3 February 2025

---
### Quick notes
- Going over this topic next lecture too
- "I go check wikipedia many times when I forget things..." - Robbie Weber, 2025
- CDF is not continuous, it's a piecewise function with integers [since it's a discrete variable]
- "Distribution" is an informal way to say "probability mass function"

### To do
- [ ] Homework 4 🔼 
- [ ] Print midterm review material 🔺 
- [ ] concept check 12
- [ ] rewatch lecture on discrete uniform distribution

---
## Lecture Notes

### Shifting A Random Variable
>For any random variable $X$, and any constants $a, b$: 
>$\mathbb{E}[aX + b] = a \mathbb{E}[X] + b$

> For any random variable $X$, and any constants $a, b$: 
> $Var(aX+b) = a^2 Var(X)$

### Discrete Random Variable Zoo
Common patterns of experiments -> flip a fair/unfair coin x times and count num of heads, or flip until you see a heads for the first time, draw a uniformly random element from a set, define an indicator random variable for an event. 

So, instead of calculating the pmf, cdf, support, expectation, and variance every time, why not calculate it just once and look it up every time?

**exactly!**

[the discrete random variable zoo is like a formula that is the solution to general types of problems, and calculating the pmf, cdf, support, expectation, is like proving that its that type of problem]

## Introducing the Zoo...

### Bernoulli Random Variable - $X\sim Ber(p)$
**Examples**
- You flip a biased coin once and want to record whether its heads.
- You define an indicator variable, and want to know whether it's 1 or not
- Did a particular bit get written correctly on the device?
- Did you guess right on a multiple choice test?
  Did a server in a cluster fail?

Generally: you have one trial, and some probability $p$ of success

$Var(X) = p(1 - p)$
$\mathbb{E}(X) = p$

[Bernoulli distribution - Wikipedia](https://en.wikipedia.org/wiki/Bernoulli_distribution)

![[bernoulli_distr.png]]

### Binomial Random Variable - $X \sim Bin(n, p)$
**Examples**:
- You flip a coin $n$ times independently, each with a probability of $p$ to see a head. How many heads are there?

Generally: How many successes did you see in $n$ independent trials, where each trial has probability $p$ of success?

$\mathbb{E}(X) = np$
$Var(X) = np(1 - p)$

[Binomial distribution - Wikipedia](https://en.wikipedia.org/wiki/Binomial_distribution)

![[binomial_distr_pmf.png]]

### Geometric Random Variable - $X \sim Geo(p)$
**Example**:
- You flip a coin until you get a heads (with probability chance of $p$). How many flips did you need?
Generally: How many independent trials are needed until the first success?

$\mathbb{E}(X) = \frac{1}{p}$
$Var(X) = \frac{1 - p}{p^2}$

[Geometric distribution - Wikipedia](https://en.wikipedia.org/wiki/Geometric_distribution)

![[geometric_distr_pmf.png]]

- Intuition - Expectation: If the probability of success is guaranteed, you have 1/1, which is obtained at the first trial.
- If you flip infinitely, as p gets larger your "chances of success" gets higher, which is what 1/p does.
- Intuition - Variance: Variance is small when p is close to 1. As p gets closer and closer to 0, you have a number close to 1 over a number very close to 0.
- Geometric Random Variables are called "memoryless" -- we're so focused on the end result that we don't care what happened in between starting and finishing.
	- Suppose you're flipping coins independently until you see a heads. The first two came up as tails. How many flips are left until you see the first head?


### Uniform Random Variable - $X \sim Unif(a, b)$
**Examples:**
- You roll a fair die
- Draw a random integer from 1 to n

$a$ is the minimum value in the support, $b$ is the maximum value. [1 is the min in a dice, 6 is the max]

$\mathbb{E}(X) = \frac{a + b}{2}$
$Var(X) = \frac{(b - a)(b - a + 2)}{12}$

[rewatch lecture on discrete uniform distribution]

[Why is the variance 12?]


---
Back to: [[CSE 312 A - Class Details]]

#ComputerScience