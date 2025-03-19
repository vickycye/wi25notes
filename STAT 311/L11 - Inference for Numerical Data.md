24 February 2025

---
### Quick notes
- Grades for midterm come back this evening or tomorrow morning
- Average is 86%?
- Lecture 11 because idk which one this is and i haven't been to class in a hot minute

### To do
- [ ] This week's practice problems
- [ ] Watch a video on one sample and two sample t tests

---
## Lecture Notes

- For numerical inference we're inferring on a different population parameter -- $\mu$

### One Sample $t$-Test
[One-Sample t-Test | Introduction to Statistics | JMP](https://www.jmp.com/en_us/statistics-knowledge-portal/t-test/one-sample-t-test.html)
Need: $\mu$ of population
Conditions:
- Independent
- Continuous
- Random sampling

It's important to have a large sample size because of the Central Limit Theorem [more normally distributed]

What is a t-distribution?
- Also has a bell shape, but its tails are thicker than the normal dsitribution
- Observations are more likely to fall beyond 2 standard deviations from the mean
- Extra thick tails are helpful for resolving our problem with a less reliable estimate of the SE since n is small
- Always centered at zero
- Has a single parameter: **degrees of freedom** (df)

Since we used the z distribution to create confidence intervals and perform hypothesis testing, we'll do the same for the t distribution too

Confidence Interval format: $\text{point estimate} \pm ME$
Now, we will use $\bar{x}$ as the point estimate and $t^*$ as the critical value.

Test statistic for inference on a small sample mean: (n < 30), using df = n - 1 is 
$$T_{df} = \frac{\text{point estimate ($\bar{x}$)} - \text{null value}}{SE}$$

How to calculate p value in R: 
`2 * pt(t-value, df, lower.tail = TRUE/FALSE)`

### Two Sample $t$-Test
Used to determine if there is a significant difference between the means of two independent groups. 

When two sets of observations that are corresponding, they are said to be <span style="color:rgb(255, 192, 0)">paired</span>.
To analyze paired data, it is often useful to look at the difference in outcomes of each pair of observations.


---
Back to: [[STAT 311 A - Class Details]]

#Stats