5 March 2025

---
### Quick notes
- ROBBIE EXTENDED HOMEWORK TO FRIDAY YAYAYAYAA

### To do
- [ ] Finish homework 7--due Friday
- [ ] Concept check 23
- [ ] Study for quiz
- [ ] do practice quiz


---
## Lecture Notes

So far we've been given the rules for an experiment, given the event we're interested in, and we calculate what the probability is. 

Now, we're trying to figure out what the rest of the rules of the experiment are--given some of the rules of the experiment and also given what happened.

**Example**
Suppose you flip a coin independently 10 times, and you see 
HTTTHHTHHH
What is your estimate of the probability the coin comes up heads?

Robbie says you can logically defend any of the options:
- $\frac{6}{10}$ [given from the information we have, there are 6/10 heads]
- $\frac{5}{10}$ [coin is close to fair in simulation but not exactly fair--most coins in the real world are fair.]
- $\frac{5}{10} < x < \frac{6}{10}$ [finding one more head and one more tail]

Mentioned: [Maximum a posteriori estimation - Wikipedia](https://en.wikipedia.org/wiki/Maximum_a_posteriori_estimation)

### MLE for discrete RVs
Idea: We have the results we got, and high probability events happen more often than low probability events.

We're trying to consider all the possibilities of the missing piece of information we don't have, and then putting them into a "distribution" and determine which one was the highest--which is the one that gives you your prediction BECAUSE high probability events happen a lot. 

New notation:
Formally, we're estimating a parameter of the experiment.
The likelihood of an event $E$ under a parameter $\theta$ is:

$\mathcal{L}(E; \theta)$  is the probability of the event $E$ happening when the experiment is run with $\theta$, the piece of information we don't know. [L(event; missing information)]
- We'll use the notation $\mathbb{P}(E; \theta)$ for the probability when running with parameter $\theta$ where the semicolon mens extra rules rather than a conditioning.
- We will choose $\hat{\theta} = \text{argmax}_{\theta} \mathcal{L}(E; \theta)$ [argmax is give me an input, find the maximum output]
- To find the maximum of a function, see [How to Find Maximum and Minimum Values of a Function? - GeeksforGeeks](https://www.geeksforgeeks.org/how-to-find-maximum-and-minimum-values-of-a-function/)

[There are other examples where theta could be the mean of the distribution etc. It doesn't have to be a probability. It's just some aspect of the experiment you don't know.]

For likelihood, we need to remember that $\theta$ is the one changing, not $X$. 

**Maximum Likelihood Estimator**
>$$\hat{\theta} = \text{argmax}_{\theta} \mathcal{L}(E; \theta)$$

Theta without hat is variable, theta with hat is number. 

**Example**
For the coin problem:
$\mathcal{L}(HTTTHHTHHH; \theta) = \theta^6 (1 - \theta)^4$
Where is $\theta$ maximized? CALCULUS!!!
$$\frac{d}{d\theta} \theta^6 (1-\theta)^4 = 6\theta^5 (1-\theta)^4 - 4\theta^6 (1 - \theta)^3$$
Set to 0 and solve -> $\theta = \frac{3}{5}$

We have the function on the closed interval $[0, 1]$. Since $\mathcal{L}()$ is a continuous function, the maximum has to be either at the endpoint or where the derivative is 0. We can test all these critical points and see which one's the maximum.

### Math tricks to compute derivatives
The product rule isn't fun so we should use logs!!
$$\ln(a \cdot b) = \ln a + \ln b$$
We can still take the max, we just have to take the log of the estimator too -> 
$$\text{argmax}_{\theta} \ln(\mathcal{L}(E; \theta)) = \text{argmax}_{\theta}\mathcal{L}(E; \theta)$$
[we can do this because ln is an increasing function]

**Example**
$\frac{d}{d\theta} 6 \ln \theta + 4 \ln (1 - \theta)$ = $\frac{6}{\theta} - \frac{4}{1 - \theta}$
Set it to 0: $\frac{6 - 6 \theta - 4\theta}{\theta - \theta^2} \implies \theta = \frac{3}{5}$ [this math is wrong but yeah]
Take second derivative: $\frac{d^2}{d\theta^2} -\frac{6}{\theta^2} - \frac{4}{(1 - \theta^2)} < 0$ everywhere, so any critical point must be a maximum.

### For continuous RVs
We can't use the probability bc all of them are 0s, but we can use the density instead.
>$$\mathcal{L}(x_{1}, x_{2}, \dots, x_{n}; \theta) = \prod f_{X}(x_{i}; \theta)$$

**Eaxmple**
Suppose you get values $x_1, x_2, \dots , x_{n}$ from independent draws of a normal RV $\mathcal{N}(\mu, 1)$, where $mu$ is unknown.
$$\mathcal{L}(x_{i}; \mu) = \sum_{i = 1}^n \ln\frac{1}{\sqrt{ 2 \pi }} -\frac{1}{2}(x_{i} - \mu)^2$$
[When you take the ln of everything, the Multiply becomes a Sum. This is the property of logarithms when you take the ln of a * b * c, you get ln a + ln b + ln c]

Next lecture we take derivative and set to 0 and solve.

---
### Concept Check 23

>What is the general definition of the likelihood $\mathcal{L}(x; \theta)$ if we are estimating a parameter $\theta$ of a **discrete random variable** given some i.i.d. samples $x=(x_{1},\dots,x_{n})$?

The definition of the maximum likelihood estimator for discrete RVs is $\mathcal{L}(x; \theta) = \prod_{i = 1}^{n} p_{X}(x_{i}; \theta)$ 
The definition of the maximum likelihood estimator for continuous RVs is $\mathcal{L}(x; \theta) = \prod_{i = 1}^n f_{X}(x_{i}; \theta)$

>What about if we're estimating for the $\ln \mathcal{L}(x; \theta)$?

We can apply a natural log function [because its easier to differentiate than normal logs] to both sides of the equation:
$$\ln \mathcal{L}(x; \theta) = \ln \left( \prod_{i = 1}^n p_{X}(x_{i}; \theta) \right) = \sum_{i = 1}^n \ln p_{X}(x_{i}; \theta)$$
Similarly, for continuous distributions, we have: 
$$\ln \mathcal{L}(x; \theta) = \sum_{i = 1}^n \ln f_{X}(x_{i}; \theta)$$

>Why do we use log estimating?

Because its easier to differentiate with logs--while still maintaining the same shape of the function. 

>Why can we maximize the log-likelihood rather than the likelihood?

Because log is a monotone increasing function and preserves the argmax value of a function.

>Suppose $x_{1}, x_{2}, \dots, x_{n}$ are iid samples from $Geo(p)$ where $p$ is unknown. Let's compute the MLE of $p$ together.
>Select all equivalent formulas for the correct log-likelihood below.

Geo(p) pmf: $(1 - p)^{k - 1} p$, this is a discrete RV
We'd have $$\ln \mathcal{L}(x; p) = \ln \left( \prod_{i = 1}^n (1-p)^{k - 1} p \right) = \sum_{i = 1}^n \ln \left[ (1 - p)^{k - 1}p \right] = n \cdot \ln p + \sum_{i = 1}^n \left[ (x_{i} - 1) \ln(1 - p) \right]$$
>What is $\hat{p}$, the MLE of $p$, in terms of the data $x_{1}, \dots, x_{n}$?

We have to calculate the first derivative of the log-likelihood function:
$$\frac{d}{dp} \ln \mathcal{L}(x; p) = \frac{n}{p} + \frac{n}{1 - p} - \frac{1}{1 - p} \cdot \sum_{i = 1}^n x_{i}$$
Then, we set the first derivative to 0, so we have
$$\begin{align} \\
	\frac{n}{\hat{p}} + \frac{n}{1 - \hat{p}} - \frac{1}{1 - \hat{p}} \sum_{i = 1}^n x_{i} &= 0 \\ 
	n\left( \frac{1}{\hat{p}} + \frac{1}{1 - \hat{p}} \right) &= \frac{1}{1 - \hat{p}} \sum_{i = 1}^n x_{i} \\ \\
\frac{n}{\hat{p}(1 - \hat{p})} &= \frac{1}{1 - \hat{p}} \sum_{i = 1}^n x_{i} \\ \\
\hat{p} &= \frac{n}{\sum_{i = 1}^n x_{i}}
\end{align}
$$


>Pretend the samples you saw were $x = (2, 5, 3, 6, 8)$. What is the MLE $\hat{p}$?

$$\hat{p} = \frac{5}{24}$$


---
Back to: [[CSE 312 A - Class Details]]

#ComputerScience