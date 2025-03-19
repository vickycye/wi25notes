26 February 2025

---
### Quick notes
- 

### To do
- [ ] Submit lab 7 by thursday evening
- [ ] Watch crash course ANOVA video at the end of the document

---
## Lecture Notes
- When testing the difference of two means, we take the difference of them and compare it with 0. 
- The parameter of interest is the average difference between the point prices of all population_1 and population_2 values.
- The point estimate is the average difference between the point prices of sample_1 and sample_2 values

Standard error for 2 sample t test:
$$SE = \sqrt{ \frac{s_{1}^2}{n_{1}} + \frac{s_{2}^2}{n_{2}} }$$
degrees of freedom is minimum from the two sample sizes - 1

### ANOVA test
- "Analysis of variance"
- This is not the same as a MANOVA test, which includes multiple variables. See [Difference Between ANOVA and MANOVA](https://spss-tutor.com/blogs/difference-between-manova-and-anova.php#:~:text=ANOVA%20mainly%20checks%20the%20differences,more%20than%20one%20dependent%20variable.) for more information

For ANOVA tests we use the `F` statistic. Null hypothesis is that all the $k$ means are equal. Alternative hypothesis is that at least one mean is different from the others.

$$F = \frac{\text{variability between groups}}{\text{variability within groups}}$$

Large F statistics lead to smaller p-values, since if the variability between groups is large and the variability between groups is small, then we're more likely to reject the null hypothesis.

If there are only two groups, then the t-test and ANOVA tests are equivalent. 

When there are more than two groups, ANOVA compares the sample means to an overall <span style="color:rgb(255, 192, 0)">grand mean</span>.

![[f_distribution.png]]

ANOVA degrees of freedom:
- groups: $df_{G} = k - 1$, where $k$ is the number of groups
- total: $df_{T} = n - 1$, where $n$ is the total sample size
- error: $df_{E} = df_{T} - df_{G}$

The sum of squares between groups (SSG) measures the variability between groups, 
$$. $$
There also an SST, which means sum of squares total

degrees of freedom = $n - k$. 

$$F = \frac{MSG}{MSE} = \frac{\frac{SSG}{k - 1}}{\frac{SSE}{n - k}}$$
[ANOVA: Crash Course Statistics #33 - YouTube](https://www.youtube.com/watch?v=oOuu8IBd-yo)

The p-value is the probability that there is a significant difference between the between-group and within-group variability. So, if the p-value is sufficiently small, we will reject the null hypothesis saying that there is convincing evidence that the average sample mean is different for at least one group. 

You can do pairwise tests to find out which means differ... but we will find that out next Monday



---
Back to: [[STAT 311 A - Class Details]]

#Stats