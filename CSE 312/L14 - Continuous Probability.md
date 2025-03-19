7 February 2025

---
### Quick notes
- Go back and learn Negative binomial and Hypergrometric distributions
- Never really knew what probability density function meant on the TI-84 (cdf and pdf)


### To do
- [ ] Start prepping for midterm on Monday
- [ ] Print homework 5
- [ ] Print section 5 worksheet
- [ ] Concept check 14
- [ ] Go back and learn Negative binomial and Hypergrometric distributions

---
## Lecture Notes

Why continuous random variables? -> we want to choose a random real number
- Central Limit Theorem [approximating discrete distributions with continuous ones]
- Tail bounds / concentration [arguing that it's unlikely that a random variable is far from its expectation]
- Predicting data in the final few weeks [ML prep]

### Continuous Random Variables
"uncountably infinite" -> real numbers, topic first introduced in sets in 311: [[L28 - Uncountability]]
- Good for enormous sample spaces

**Example**
>What's the probability that a number is between 0.4 and 0.5?
  0.10, not a trick question

If we have an infinite event space and an infinite sample space, if we want to calculate it, we get $\frac{\infty}{\infty}$, which is invalid!!

| Discrete rv                          | Continuous rv                                |
| ------------------------------------ | -------------------------------------------- |
| pmf: $\sum_{\omega} p_Y(\omega) = 1$ | pdf: $\int_{-\infty}^{\infty} f_X(k) dk = 1$ |
|                                      |                                              |
For continuous RVs, a probability mass function isn't useful because every time we ask for an event, it will be effectively 0

### Probability density function
[Probability density function - Wikipedia](https://en.wikipedia.org/wiki/Probability_density_function)

$$\mathbb{P}(a \leq X \leq b) = c \rightarrow \int_{a}^{b} f_X(z) dz = c$$==integrating is analogous to sum==  

- $P(0 \leq x \leq 1) = 1$
$$\int_{0}^{1} f_X(k) dk = 1$$
- $P(X \text{ is negative}) = 0$ 
$$\int_{- \infty}^{0} f_X(k) dk = 0$$
- $P(.4 \leq X \leq .5) = .1$ -> roughly 1/10 of the values fall between .4 and .5
$$\int_{0.4}^{0.5} f_X(k) dk = 0.1$$


![[sd_ranges.png]]

**Example**: Let $X$ be a uniform real number between 0 and 1. What should the pdf be to make all those events integrate to the right values?
$$f_X(k) = \begin{cases} 
	0 & \text{ if } k < 0 \text{ or } k > 1\\
	1 & \text{ if } 0 \leq k \leq 1
\end{cases}$$
![[uniform_distr.png]]
[Imagine this but a is 0 and 1 is b, and we can think of c = 0.4 and d = 0.5, so the probability of the red part inside between c and d is 0.1. The height of the "function" has to be 1, since the bounds are 1]

**Now, what's the probability that the number i get is exactly 0.1?**
$$\mathbb{P}(X = 0.1) = 0$$
If you evaluate a pdf at a specific point, you get 1 -> <span style="color:rgb(255, 192, 0)">PDF doesn't work for specific values, it only works for a range. </span>

If we want to answer that question, you're gonna integrate from 0.1 to 0.1, and get 0, since the area of nothing is 0!!!

>For continuous probability spaces: impossible events have probability 0, but some probability 0 events might be possible!! by the saints! what sorcery is this? i am utterly befuzzled by the peculiarity of this situation!

- We look to see if the density is 0 at a specific event, if it is not 0, then it is possible. If it is, then it's impossible. 

**Example. What is the probability that $X \text{ is around } 0.2$**
![[l14-slides.png]]
Note: $\epsilon$ here means an arbitrarily small value, but still enough to make a difference so integration doesn't result in 0. 

The resulting ratio of the pdf of .2 and .5 tells us how likely you are to be near the area of 0.2 versus near the area of 0.5.  [aka how "dense" the probability is]

### What?
- The pdf is the number that when integrated over, gives the probability of an event [typically it's useful when finding the probability of events happening within an interval]
- Integrating over all real numbers gives 1.
- Comparing $f_X(k)$ and $f_X(l)$ gives the relative chances of $X$ being near $k$ or $l$. 

### CDF 
- Almost the exact same as the cdf in the discrete RV case
> $$F_X(k) = P(X \leq k) = \int_{- \infty}^{k} f_X(z) dz$$

How do you get from the CDF to the PDF? Take the derivative!
$$\frac{d}{dk} F_X(k) = \frac{d}{dk} (\int_{- \infty}^{k} f_X(z) dz) = f_X(k)$$
![[discrete_vs_continuous.png]]




---
Back to: [[CSE 312 A - Class Details]]

#ComputerScience