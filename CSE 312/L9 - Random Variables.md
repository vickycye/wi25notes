27 January 2025

---
### Quick notes
- An expected value is an average, not an outcome.

### To do
- [ ] Concept check 9
- [ ] Read the textbook section for Random variables
- [ ] Finish homework 3
- [ ] Review CDF from today's lecture
- [ ] Study for Quiz on Thursday
- [ ] Read Shanon Ross Textbook

---
## Lecture Notes

### Random Variable Stuff

Formally:
>$X: \Omega \rightarrow \mathbb{R}$ is a random variable. $X(\omega)$ is the summary of the outcome $\omega$. 
- Random variables are functions, but you don't really write them as functions, it's just $X = \text{ some value }$. 

$\Omega_X$ is the <mark style="background: #FFF3A3A6;">support</mark>, (aka the "range"), which is the set of values that $X$ can actually take. 
[called the "image" in 311] 

For example, the "support" for the max of two dice would be $\{ 1, 2, 3, 4, 5, 6 \}$ [since both dice can be 1 and both can be 6]

#### Probability Mass Function
$\mathbb{P}(X = x)$, or written as $p_X(x)$ -> this gives the probability of an event, with the notation as $\{ \omega: X(\omega) = x\}$. 

- A random variable partitions the sample space, $\Omega$. 

**Practice**
There are 20 balls, numbered $1,2,…,20$ in an urn. You’ll draw out a size-three subset. (i.e. without replacement) Ω = {size three subsets of 1, … , 20 }, $\mathbb{P}()$ is uniform measure. Let 𝑋 be the largest value among the three balls. If outcome is $\{4,2,10\}$ then $X = 10$. Write down the pmf of $X$.

$$p_X(x) =\begin{cases} 
      \frac{{x - 1 \choose 2}}{{20 \choose 3}} & \text{if } x \in \mathbb{N}, 3 \leq x \leq 20 \\
      0 & \text{otherwise}
   \end{cases}$$

- Numerator: You choose one ball which is the max, and then you choose how to pick the smaller two balls.
- Denominator: total number of ways to have a subset size of 3.
- Second part of the piecewise: For balls 1 and 2, you cannot have a max because the balls are drawing without replacement. We need to define "otherwise" because we need to consider for all cases, even beyond 20. 

A good check to see if the pmf is right is to see if it sums up to 1. Since it considers all the cases and its a probability distribution, it should add up to 1. 

Another good check is to see if the pmf is $\geq 0$ for all $x$, since a probability cannot be negative. 

### Describing a Random variable

The most common way to describe a random variable is the PMF. There's another representation called the cumulative distribution function (CDF) which gives the probability $X \leq x$. 

>$\mathbb{P}(\{\omega : X(\omega) \leq x\})$
>Often written as $F_X (x) = \mathbb{P}(X \leq x) = \sum_{i: i \leq x} p_X (i)$ 

Think of this as a "cumulative exam", where it sums up all the probabilities smaller than [im confused]

**Practice**
What is the CDF of $X$ where $X$ is the largest value among the three balls (drawing 3 of the 20 without replacement)

$$F_X(x) =\begin{cases} 
      \frac{{\lfloor x \rfloor \choose 3}}{{20 \choose 3}} & 3 \leq x \leq 20 \\
      0 & \text{if } x < 3 \\
      1 & \text{otherwise}
   \end{cases}$$
Good checks include:
- Is F_X (inf) = 1?
- If F_X increasing?
- Is F_X defined for all real numbers?

[Come back and review the CDF]

**MORE PRACTICE!!!**

Roll a fair die $n$ times. Let $Z$ be the number of rolls that are 5s or 6s.

$$p_Z(z) =\begin{cases} 
      {n \choose z} \cdot (\frac{1}{3})^z \cdot (\frac{2}{3})^{n - z} & \text{if } x \in \mathbb{N}, 3 \leq x \leq 20 \\
      0 & \text{otherwise}
   \end{cases}$$
1/3 ^z -> if you have exactly z 5 or 6s, and you have n - z [come back to this]

### Expectation
>The "expectation" or "expected value" of a random variable $X$ is:
>$\mathbb{E}[X] = \Sigma_{k} \cdot \mathbb{P}(X = k)$

**Example**
Flip a fair coin twice (independently). Let $X$ be the number of heads.
$\Omega = \{TT, TH, HT, HH\}$, where $\mathbb{P}()$ is uniform measure.

[write down expected value formula from the slides]

**Example**
Roll a biased die. It shows a 6 with probability 0.333 and 1, ..., 5 with probaility 2/15 each. Let X be the value of the fie. What is E[X]? 

**Practice**
[Look on slides, we skipped that one]


### Mutual Independence for Random Variables

We already talked about mutual idnependence for events (for all subsets -> equal to each event happening individually)

>X_1, X_2, ..., X_n are mutually independent if for all x_1, x_2, ..., x_n P(X_1 = x_1, etc) = P(X_1 = x_1) * the rest of them


### So what?

Independence gives us:
1. E[XY] = E[X] * E[Y]
2. Var(X + Y) = Var(X) + Var(Y)

[more practice at the end of the slide deck]

---

### Naive Bayes' Classification Task

Intro to Machine Learning

There are many types of machine learning, two being
1. Regression -- outputting a numerical value
2. Classification -- separating into groups

Steps of machine learning:
Preprocessing data -> training -> testing -> evaluation

Laplace Smoothing accounts for certain probabilities that may be zero and affect the probability of events occurring in the Bayes' formula. 

Read more here: [Laplace smoothing in Naïve Bayes algorithm | by Vaibhav Jayaswal | Towards Data Science](https://towardsdatascience.com/laplace-smoothing-in-na%C3%AFve-bayes-algorithm-9c237a8bdece)

To do this, we add 1 to the numerator in each probability calculation, and add 2 to the denominator, which is adding 1 extra value for an event WITH [the spam word], and 1 extra value for an event WITHOUT [the spam word].

Notes from Jonathan Lee: x.com/?lang=en

---
### More Knowledge from the Internet

A random variable is actually neither random nor a variable, it's a collection of events.
- But they have properties like variables and they seem "random"
Disjoint and exhaustive RVs are called discrete random variables.

Random variables are also NOT probability distributions!!!
But they can be turned into probability mass functions!! [which is like a histogram of the probability of events].

$$\mathbb{E}[Z] = \sum_{z \in \mathbb{R}} z \mathbb{P}(Z = z) \Leftrightarrow \mathbb{E}[Z] = \sum_{z \in \mathbb{R}} Z(\omega) \mathbb{P}(\omega)$$
Probability distribution formula:
- Can be useful when 
Random variable formula:

---
Back to: [[CSE 312 A - Class Details]]

#ComputerScience
