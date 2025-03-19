18 February 2025

---
### Quick Notes
- funny be i havent been to lecture in like 10 years
- No z-score memorization required
- Don't need to memorise standard deviation formula
- No need to worry about anything code related
- Survivorship bias: [Survivorship bias - Wikipedia](https://en.wikipedia.org/wiki/Survivorship_bias)

### To do
- [ ] Make cheatsheet [review past leture slides]
- [ ] Study !!
- [ ] 20 questions, most are MC, some short response
- [ ] Look @ ed for questions other people have

---
### Review Notes

### Data
#### Types
- **Numerical:** continuous (e.g. height, weight [has decimals]), discrete [whole numbers, counts]
- **Categorical:** Ordinal [education level, customer satisfaction (has direction/order)], nominal [colors, types of animals, etc. (no order)]

Example: A researcher doing a blind experiment has respondent data encoded with numbers ina  column named "respondent_id". What type of data is this? [nominal]

#### Collection Types
- **Observational studies:** collect data in a way that does not directly interfere with how the data arise [can show evidence of association but not causation]
- **Experiments:** researchers randomly assign subjects to variuos treatments in order to eatablish causual connections between explanatory and response variables. [can show evidence of causation]

Example: What is a positive association? [when one variable increases the other increases. Negative would be if one increases and the other decreases]

#### Sampling Biases
- **Non-response:** If a small fraction of the randomly sampled choose to response -> non-representative
- **Voluntary Response:** sample consists of people who volunteer to respond because they have strong opinions on the issue.
- **Convenience Sampling:** choosing respondents who are easily accessible who are more likely to be included in the sample 
-> All of these are factors into bad experiment design

Example: You send out an email to the undergrad student body asking for volunteers [non-response bias] 

#### Sampling Strategies
[What are the types of Sampling Methods? - Fynzo®](https://www.fynzo.com/blog/types-of-sampling/)
- **SRS**: mix up people and randomly pick a few
- **Stratified**: dividing people into groups and choosing an equal amount from each group
- **Cluster**: dividing people into clusters and choosing a few clusters at random
- **Multistage** sample: [find out]

![[sampling_strategies.png]]

#### Blocking
Blocking characteristics are characteristics that the experimental units come with, that we would like to control for. 
> The difference between blocking variables and explanatory variables is explanatory is the thing you're measuring to see how it affects an outcome, and you don't care about blocked variables (they generally affect results too)

### Statistics you should know (maybe how to calculate)
- mean
- median
- standard deviation/variance [what's the difference?]
- 1st quartile, 3rd quartile
- IQR

### Probability you should know
- expected value (mean) [pdf for continuous variables, summation for discrete variables]
- disjoint sets [cannot occur at the same time]
- complementary sets [A and A complement = 1]
- independence [remember two independence equivalent conditions]

#### Distribution Types
- for a left skew, mean < mode for left skew, mean = mode for no skew, mean > mode for right skew

### Normal Distribution
- Empirical rule [write it down, anything 3 sd away from the mean is an outlier]

### Binomial Distribution
- The number of successes in a sequence of n independent experiments, each being a success/failure with the probability of success being p
	If $np \geq 10$ and $n(1 - p) \geq 10$ then you can approximate it with a normal distribution $$\mathcal{N}(np, np(1 - p))$$

Covariance:
$$2 \cdot Cov(X, Y) + Var(X) + Var(Y) $$
### Z-Scores
Standardising the normal distribution:
$$z = \frac{x - \mu}{\sigma}$$

### Hypothesis-Testing
compares two opposite statements about a population and uses sample data to decide which one is more likely to be correct. $H_0$ is the null hypothesis, the starting assumption, $H_{\alpha}$ is the alternative hypothesis, which is what you're trying to prove is true. 

[Need to know Type 1 and Type 2 errors]
Type 1: false positive [incorrectly reject H_0]
Type 2: [incorrectly fail to reject H_0 when H_a is true]

### Experimental Design
1. Control -> control the effect of confounding variables
3. Randomize -> to get a population-representative sample
4. Replicate -> collect a sufficiently large sample or replicate the entire study
5. Block -> if there are variables that are known or suspected to affect the reponse variable, first group subjects into blocks based on the variables, then randomize cases within each block to treatment groups.



---
Corresponding Lecture: Idk I haven't gone to any

Back to: [[STAT 311 A - Class Details]]

#Stats
