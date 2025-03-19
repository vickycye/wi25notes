15 January 2025

---
### Quick notes
- Quantiles vs. quartiles
- Median and IQR are robust to skewness and outliers than mean and std. 
- <mark style="background: #FFF3A3A6;">each question that she posts in class is likely to appear on the midterm </mark>

### To do
- [x] Submit lab 2 tomorrow ✅ 2025-01-16
- [ ] read textbook
- [ ] review slides on log transformations
- [ ] review slides on covariance and correlation
- [x] Extra credit activity for this class? Tonight? ✅ 2025-01-16

---
## Lecture Notes

### Variance
$$s^2 = \frac{\sum_{i = 1}^{n} (x_i - \bar{x}^2)}{n - 1}$$
- variance is std squared
- square deviations because otherwise there will be negative and positive numbers, and they might cancel out
- divide by $n - 1$ because there is 1 degree of freedom [what if there were more degrees of freedom, do you just subtract more?]
	- "unbiased estimator" -> sample variance becomes an unbiased estimator of the population variance. If we were to divide by $n$, the sample variance would tend to underestimate the true variance. This is because the sample mean is typically closer to the individual data points than the true population mean, making the squared differences a little smaller.

### Standard Deviation
$$s = \sqrt{v}$$
### Median (also called 50th percentile)
- Value that splits the data in half when ordered in ascending order
- If there is an even number of observation, the median takes the average of the two values in the middle

| 25th percentile  | Q1     |
| ---------------- | ------ |
| 50th percentile  | median |
| 75th percentile  | Q3     |
| 100th percentile | max    |
The Interquartile Range is Q3 - Q1. 

### Box plots
- aka whisker plots
- two "whiskers" mark where the outliers begin
	- max upper whisker = $Q3 + 1.5 \times IQR$
	- max lower whisker = $Q1 - 1.5 \times IQR$
- The box represents Q1, median, and Q3. 

### Scatterplots
- useful for visualizing the relationship between 2 numerical variables

$\rho$ = correlation -> line of best fit -> linear regression

<mark style="background: #FFF3A3A6;">covariance</mark> measures the joint variation of two variables X and Y. 
$$cov(X, Y) = \frac{\sum_{i = 1}^{n} (x_i - \bar{x}) (y_i - \bar{y})}{n - 1}$$




---
Back to: [[STAT 311 A - Class Details]]

#Stats