12 February 2025

---
### Quick notes
- Midterm is at night again in PAA :D
- less variance = more dense in the mean, smaller spread
- more variance = less dense in the mean, bigger spread
- Next time = Central Limit Theorem

### To do
- [ ] Finish homework 5 [Due Friday]
- [ ] Print out practice exams from website


---
## Lecture Notes

I never want to do another integral calculation by hand again..

<span style="color:rgb(255, 192, 0)">For continuous random variables, whenever we're computing the probability that a value is greater than a value, we want to do 1 - value</span>

$$\mathbb{P}(X \geq 1) = 1 - \mathbb{P}(X < 1) = 1 - \mathbb{P}(X \leq 1)$$
This is because it's easier to calculate the area to the left for any continuous variable.

### Continuous Normal Random Variables (Gaussian RV), $X \sim \mathcal{N}(\mu, \sigma^2)$

$$f_X(x) = \frac{1}{\sigma \sqrt{2 \pi }} e^{-\frac{(x - \mu)^2}{2 \sigma^2}}$$
- The formula is symmetric around $\mu$, which means that the mean is also the medium, so the expectation must also be $\mu$


![[continuous_normal_distr.png]]

- e to the negative power is "exponential decay"

Changing the variance changes the density of the graphs at different places [height and squish]
Changing the mean effectively translates the graph by the value of the mean [negative value shifts left, etc.]

If you scale and shift a normal distribution, you still get a normal distribution

#### Standardising a Normal Variable

$Y = \frac{X - \mu}{\sigma}$ to turn $X \sim \mathcal{N}(\mu, \sigma^2)$ into $Y \sim \mathcal{N}(0, 1)$

There is no closed form of the CDF for a standard normal distribution 
[Normal distribution - Wikipedia](https://en.wikipedia.org/wiki/Normal_distribution)

Instead, you can have this table 
![[zscore-table.png]]

We only have one table because every normal is different, so when you want to calculate the area, you should standardise the distribution then look it up in this table.

Very simple, very demure
$\mathbb{E}[X] = \mu$
$Var(X) = \sigma^2$

**Example**
Let $X \sim \mathcal{N}(3, 2)$, what is the probability that $1 \leq X \leq 4$

$\mathbb{P}(1 \leq X \leq 4)$
$= \mathbb{P}(\frac{1 - 3}{\sqrt{2}} \leq \frac{X - 3}{\sqrt{2}} \leq \frac{4 - 3}{\sqrt{2}})$
$= \mathbb{P}(\frac{-2}{\sqrt{2}} \leq \frac{X - 3}{\sqrt{2}} \leq \frac{1}{\sqrt{2}})$
$= \mathbb{P}(-1.414 \leq Y \leq 0.7071)$
$= \mathbb{P}(Y \leq 0.7071) - \mathbb{P}(Y \leq -1.414)$
$= \phi(0.71) - \phi(-1.41)$
$= \phi(0.71) - (1 - \phi(1.41))$
$= something$

Since we're calculating the probability of a thing happening between two values, subtract the smaller probability from the larger probability. 


---
Back to: [[CSE 312 A - Class Details]]

#ComputerScience