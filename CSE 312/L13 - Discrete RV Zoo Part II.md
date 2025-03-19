5 February 2025

---
### Quick notes
- Lecture was Online due to snow

### To do
- [x] Concept check 13 ✅ 2025-02-05
- [x] Submit homework 4 ✅ 2025-02-05

---
## Lecture Notes

### Poisson Distribution - $X \sim Poi(\lambda)$
Used when:
- we want to count the number of times something happens in some interval of time
- we know the average/expectation
- each occurrence is independent of the others
- VERY LARGE number of potential sources for those events, which are rare.

Applications:
- How many snow storms in Seattle in a year
- How many customers visit a bakery in an hour

==A Poisson Distribution is a model of the real world -- the events may not be independent ==

$\lambda =$ the average number of incidents in a time interval
$X =$ the number of incidents seen in a particular interval
Support = $\mathbb{N}$
$p_X(k) = \frac{\lambda^k e^{- \lambda}}{k!}, k \in \mathbb{N}$
$F_X(k) = e^{- \lambda} \sum_{i = 0}^{\lvert k \rvert} \frac{\lambda^i}{i!}$ [This is very similar to a taylor series!!!]
$\mathbb{E}(X) = \lambda$
$Var(X) = \lambda$

==The Poisson acts like a certain limit as $n \rightarrow \infty$ but $np$ remains constant==

![[poisson_distribution.png]]

### Negative Binomial - $X \sim NegBin(r, p)$
- Run independent trials with probability $p$. How many trials do you need for $r$ successes?

$PX(k) = {k - 1 \choose r - 1} (1 - p)^{k - r} p^r$
$Var(X) = Var(Z_1 + Z_2 + \cdots + Z_r) = r \cdot \frac{1-p}{p^2}$
$\mathbb{E}(X) = \mathbb{E}(Z_1 + Z_2 + \cdots + Z_r) = r \cdot \frac{1}{p}$

![[negativebinomial_distr.png]]

i.i.d. means independent & identically distributed -> identical pmfs 

### Hypergeometric - $X \sim HypGeo(N, K, n)$
- similar to geometric except you draw things without replacement

---
Back to: [[CSE 312 A - Class Details]]

#ComputerScience