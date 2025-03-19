5 March 2025

---
### Quick notes
- 

### To do
- [ ] Week 8 practice problems
- [ ] Week 9 practice problems

---
## Lecture Notes

Recap from last lecture--conditions for the least squares line:
1. Linearity
2. Nearly normal residuals [Can check using a histogram of residuals]
3. Constant variability

The strength of the fit of a linear model is most commonly evaluated using $R^2$. It's calculated as the square of the correlation coefficient.

### Types of Outliers in Linear Regression
[7.4: Types of Outliers in Linear Regression - Statistics LibreTexts](https://stats.libretexts.org/Bookshelves/Introductory_Statistics/OpenIntro_Statistics_(Diez_et_al)./07%3A_Introduction_to_Linear_Regression/7.04%3A_Types_of_Outliers_in_Linear_Regression)
**High-leverage:** horizontally far from the line/cloud -- strongly influence the slope of the least squares line
**Influential:** If a high-leverage point does actually invoke influence on the line's slope.

Influential points don't **always** reduce $R^2$, they don't **always** change the intercept of the regression line--they can **sometimes** do that.

### Inference for Linear Regression
[STATS4STEM](https://www.stats4stem.org/inference-linear-regression)
test statistic $T = \frac{\text{point estimate - null value}}{SE}$
Point estimate = $b_{1}$ is the observed slope
$SE_{b1}$ is the standard error associated with the slope.
Degrees of freedom associated with the slope is $df = n - 2$, where $n$ is the sample size. [We lose 2 df because we are estimating 2 parameters]

**Eaxmple**
A 1% increase in Hispanic residents in a zip code area in LA is associated with a 0.75% decrease in % of college grads. 


---
Back to: [[STAT 311 A - Class Details]]

#Stats