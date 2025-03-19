7 March 2025

---
### Quick notes
- 

### To do
- [ ] Homework 8 released yesterday night -- print out
- [ ] Finish homework 7 and submit today [try not to use late days]

---
## Lecture Notes

Discrete: Write likelihood -> take log -> take derivative -> confirm maximum
For continuous we just use density instead of probabilities.

For a normal random variable (pdf taken from zoo)
$$\mathcal{L}(x_{i}; \mu) = \prod_{i = 1}^n \frac{1}{\sqrt{ 2 \pi }} \exp\left( -\frac{1}{2}(x_{i} - \mu)^2 \right)$$
Take ln:
$$\mathcal{L}(x_{i}; \mu) = \sum_{i = 1}^n \ln \left(\frac{1}{\sqrt{ 2 \pi }}\right) -\frac{1}{2}(x_{i} - \mu)^2$$
Differentiate:
$$\frac{d}{d\mu} \ln(\mathcal{L}) = \sum_{i = 1}^n x_{i} - \mu$$
Set the derivative to 0 and solving, we get 
$\sum_{i = 1}^n x_{i} - \mu = 0 \to \sum_{i = 1}^n x_i = \mu \cdot n \to$ $\hat{\mu} = \frac{\sum_{i = 1}^n x_{i}}{n}$.
Check using the second derivative test: $\frac{d^2}{d \mu^2} \ln(\mathcal{L}) = -n$

### In general
Given: an event $E$ [usually n iid samples from a distribution with an unknown parameter theta, can be any parameter]
1. Find the likelihood $\mathcal{L}(E; \theta)$ [usually prod P(x; theta) for discrete and prod f(x; theta)]
2. Maximize the likelihood
	1. Take the log [ln]
	2. Set derivative to 0 and solve
	3. Use the second derivative test to confirm you have a maximizer

**What happens when we know our data is normal but both the mean and the variance is unknown?**
$$\mathcal{L}(x_{1}, \dots, x_{n}; \theta_{\mu}, \theta_{\sigma^2})$$
We still calculate this, but with a different formula.
[do all the math from the lecture slides]

Now instead of taking regular derivatives, we have to take partial derivatives because we have multiple parameters to solve for. 
$$\begin{align} \\
\frac{d}{d\theta_{\mu}} &= \sum_{i = 1}^n \ln \left( \frac{1}{\sqrt{ \theta_{\sigma^2} 2 \pi}} \right) - \frac{1}{2} \cdot \frac{(x_{i} - \theta_{\mu})^2}{\theta_{\sigma^2}} \\ 
&= \sum_{i = 1}^n \frac{x_{i} - \theta_{\mu}}{\theta_{\sigma^2}}
\end{align}$$
We take the partial derivative [remember to treat the other variables as constants] 
Since we treat the variance as a constant, if we set the equation equal to 0 and solve, we still get the same thing. 
"variance shows up and disappears"

My attempt:
$$\begin{align} \\
\frac{d}{d\theta_{\sigma}} &= \sum_{i = 1}^n \ln \left( \frac{1}{\sqrt{ \theta_{\sigma^2} 2 \pi}} \right) - \frac{1}{2} \cdot \frac{(x_{i} - \theta_{\mu})^2}{\theta_{\sigma^2}} \\  \\
&= \sum_{i = 1}^n \ln \left( (\theta_{\sigma^2} 2\pi )^{-\frac{1}{2}}\right) - \frac{1}{2} \sum_{i = 1}^n \cdot (x_{i} - \theta_{\mu})^2 \theta_{\sigma^2}^{-1}  \\
&= -\frac{1}{2} \sum_{i = 1}^n \ln(\theta_{\sigma^2} 2 \pi) - \frac{1}{2} \sum_{i = 1}^n
\end{align}$$
![[MLE_variance_calculation.png]]

When we calculate the variance, we need information about the mean. Now, when we try to find the variance, and then we can plug in $\theta_{\mu}$ to find $\theta_{\sigma}$.


### Bias in Estimators
>An estimator $\hat{\theta}$ is unbiased if $\mathbb{E}[\hat{\theta}] = \theta$

This means that we're not consistently overestimated or underestimated. "When we actually run the experiment, what will happen"

[Is there a significant difference between biased estimators that are either below theta or above theta?]

If we generalize a coin flip simulation and we want to see the numebr of heads, is the estimation biased or unbiased?

$E[num heads/ total flips]$ =  $\frac{\theta n}{n} = \theta$

[What is it biased from?]




---
Back to: [[CSE 312 A - Class Details]]

#ComputerScience