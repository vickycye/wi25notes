21 February 2025

---
### Quick notes
- 

### To do
- [ ] Start Homework 6
- [x] Concept check ✅ 2025-02-21

---
## Lecture Notes

We used to do multiple "independent" random variables, but now we're gonna talk about multiple variables that aren't necessarily independent. 

A "joint distribution" is the probability of 2+ random variables occurring together. It defines the likelihood of different combinations of values for these variables.

Like normal random variables, there are 2 different types: discrete and continuous. 

Some notes on application: machine learning uses dependence to provide recommendation algorithms, so multiple random variables that might be dependent on each other is getting closer to where we want to be. 

Joint 
$$p_{X, Y} (x, y) = \mathbb{P}(X = x \cap Y = y)$$
which has properties of being non-negative and the total probability sums to 1:
$$\sum_x \sum_y \mathbb{P}(x, y) = 1$$
### Marginalization
This is the cs term. 
Dishita said "maginal like vaginal" :skull:

It's the process of summing over one variable to obtain the probability distribution of another. We can derive the marginal probability of a single random variable from the joint distribution. 
$p_X(x) = \sum_y p(x, y)$ , $p_Y(y) = \sum_x p(x, y)$  

For example, if we have $U$ which is the lowest roll out of 2 independent dice rolls, and if we have $V$ which is the highest roll out of the two, the following pmf of $p_{U, V}(u, v)$ would be:

|         | $U = 1$        | $U = 2$        | $U = 3$        | $U = 4$        |
| ------- | -------------- | -------------- | -------------- | -------------- |
| $V = 1$ | $\frac{1}{16}$ | 0              | 0              | 0              |
| $V = 2$ | $\frac{2}{16}$ | $\frac{1}{16}$ | 0              | 0              |
| $V = 3$ | $\frac{2}{16}$ | $\frac{2}{16}$ | $\frac{1}{16}$ | 0              |
| $V = 4$ | $\frac{2}{16}$ | $\frac{2}{16}$ | $\frac{2}{16}$ | $\frac{1}{16}$ |
Why is it a table? It's most commonly expressed as a table.

#### Expectations of Joint Functions
>$$\mathbb{E}[g(X, Y)] = \sum_{y \in \Omega_X} \sum_{y \in \Omega_Y} g(x, y) \cdot p_{X, Y}(x, y)$$

#### Conditional Expectation
>$$\mathbb{E}[X | E] = \sum_{x \in \Omega_X} x \cdot \mathbb{P}(X = x | E)$$
>$$\mathbb{E}[x | Y = y] = \sum_{x \in \Omega_X} x \cdot \mathbb{P}(X = x | Y = y)$$

#### Linearity of Expectation
>$$\mathbb{E}[(aX + bY + c) \vert E] = a\mathbb{E}[x | E] + b\mathbb{E}[Y \vert E] + c$$

### Law of Total Expectation
>$$\mathbb{E}[X] = \sum_{i = 1}^{n} \mathbb{E}[X \vert A_i] \cdot \mathbb{P}(A_i)$$
>$$\mathbb{E}[X] = \sum_{y \in \Omega_y} \mathbb{E}[X \vert Y = y] \cdot \mathbb{P}(Y = y)$$

**Practice**
Consider the following joint PMF of random variable XX and YY. $P(X=1,Y=3)=P(X=2,Y=5)=P(X=2,Y=1)=P(X=2,Y=2)=\frac{1}{4}​$
What is the PMF of $XY$? ($XY$ is the random variable you get by multiplying $X$ and $Y$).

$$\mathbb{P}(XY = k) = \begin{cases}
	1/4 & k = xy = 1 \cdot 3 = 3 \\
	1/4 & k = xy = 2 \cdot 5 = 10 \\
	1/4 & k = xy = 2 \cdot 2 = 4 \\
	1/4 & k = xy = 2 \cdot 1 = 2
\end{cases}$$

What is $\mathbb{P}(X = 1)$?
-> $\frac{1}{4}$

What is $\mathbb{P}(X = 2)$? [Can also do by complementarity]
-> $\frac{3}{4}$


To find $\mathbb{E}[XY]$, use:
$$\mathbb{E}[XY] = \sum_{x}\sum_{y} xy \cdot p_{X, Y}(x, y)$$

What is $\mathbb{E}[XY]$?
$$\begin{align}
 \mathbb{E}[XY] &= \frac{2 \cdot 1}{4} + \frac{2 \cdot 2}{4} + \frac{1 \cdot 3}{4} + \frac{2 \cdot 5}{4} \\
&= \frac{1}{2} + 1 + \frac{3}{4} + \frac{5}{2}  \\
&= 4 + \frac{3}{4} \\
&= \frac{19}{4}
\end{align}$$


---
Back to: [[CSE 312 A - Class Details]]

#ComputerScience