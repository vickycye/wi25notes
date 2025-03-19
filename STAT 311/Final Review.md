13 March 2025

---
### Quick notes
- Mostly just stuff after the midterm

### To do
- [ ] Practice problem sets for second half of quarter
- [ ] 

---
## Review Notes

- 95% for z-table is 1.96
- Remember empirical rule

### Things to remember
Focus on chapters 7 and 8 for the exam. Chapter 5 is a good thing to review because we'll use this in chapter 7.

**t-distribution**
Used when the population standard deviation is unknown, but the data seems nearly normal. You can also use it on small sample sizes like < 30. 
Assumptions:
- Nearly normal [Can't really tell for small sample sizes, but we can think of where the data came from--i.e. would we expect it to be symmetric?]
- Independence [Was the data randomly sampled? can you reasonably assume that the data points would not affect each others values? Or is it less than 10% of the population?]

[What happens as the df -> infinity?]
- Means the t-distribution approaches the standard normal distribution, meaning the differences between the two become negligible.

**Paired t-Test**
With paired exams, it's the same formula, but we're just looking at the differences between two observations. 
Assumptions:
- Independence: independent within groups [often verified with SRS]
- No extreme skew

**Example on two sample t-test**
Examine differences between older and younger siblings on perceived life satisfaction. 10 older, 10 younger adults were given the test. 

Null hypothesis: There is no difference between the mean life satisfaction scores of older and younger adults.
Alternative hypothesis: There is a difference between the mean life satisfaction scores of older and younger adults.
Degrees of freedom: 9
Statistic: $\frac{16.4}{\sqrt{7.53424 + 7.29316}}$ -> $t = 4.259$

**ANOVA test** - F statistic
Similar to t-test, but here's the difference

Null hypothesis: the means are all the same
Alternative hypothesis: at least one mean is different

Assumptions:
- Independence: observations should be independent within and between groups [SRS from <10% of population, conditions is satisfied]
- Nearly normal: within each group

$$F = \frac{\text{variability between groups}}{\text{variability within groups}} = \frac{MSB}{MSE} = \frac{\frac{SSB}{(k - 1)}}{\frac{SSE}{(N - k)}} = \frac{\frac{\sum n_{i}(\bar{x}_{i} - \bar{x})^2}{(k - 1)}}{\frac{\sum \sum ({x} - \bar{x}_{i})^2}{(N - k)}}$$

**Bootstrapping & Permutation Tests**
Bootstrapping is for calculating confidence intervals and permutations tests are for comparing means. 
>Why would we want to use these methods over more theoretical methods?

Sometimes we have data that violate normality assumptions (bootstrapping and permutation tests work regardless). Theoretical methods rely on large-sample approx. so we can use these methods for smaller datasets. When the statistic of interest [median, correlation, ML metric] lacks a known sampling distribution, bootstrapping can estimate confidence intervals empirically. 



## Cheatsheet worthy formulas

One sample t-test
$$df = n - 1$$
$$T_{df} = \frac{\text{point estimate - null value}}{SE}$$
$$SE = \frac{s}{\sqrt{ n }}$$
$$\text{point estimate} \pm t^* \times SE$$

Two sample t-test
$$T_{df} = \frac{\text{point estimate - null value}}{SE}$$
$$SE = \sqrt{ \frac{s_{1}^2} {n_{1}} + \frac{s_{2}^2}{n_{2}}}$$
$$df = min(n_{1} - 1, n_{2} - 1)$$

---

## From Slides
*Residuals* are leftovers from the model fit. [Data = Fit + Residual]
-> difference between observed and predicted values ($e_{i} = y_{i} - \hat{y}_{i}$) [Draw residual plot]

*Correlation* describes the strength of the linear association between two variables. 
- Between -1 and 1
- 0 = no linear association

### Least Squares Regression




---
Back to: [[STAT 311 A - Class Details]]

#Stats