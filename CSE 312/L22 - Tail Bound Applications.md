3 March 2025

---
### Quick notes
- Aka "concentration inequalities" -- because in some cases the "probability is most concentrated around the expectation"
- Tail bounds are useful when an experiment is random, but the expected value is the desired outcome. 
- Expected experiment mean -> true value of population mean
- Useful when an experiment is complicated and you just want the probability to be small
- Choosing a minimum n for a poll
- Designing probabilistic algorithms
- Next lecture we're working on estimators

### To do
- [ ] Finish gradescope homework questions
- [ ] Finish question 1
- [ ] Concept check 22
- [ ] MAKE A CONNECTION BETWEEN THIS CLASS AND STATS
- [ ] Watch video from one of the last slides that explains differential privacy.

---
## Lecture Notes

#### Quick Recap

**Markov**: Comparing min/max values, Cases with only mean data, Non-negative variables, Rough upper bound estimates. 
**Example**
- Estimating project cost upper limit
- Queue wait time prediction
- Power usage estimation
- Visitor count estimates
- Call duration
- Monthly expenses. 

**Chebyshev**: Comparing deviation from mean, Having mean and variance data, No need to know distribution shape. [Good for when variance is high]
**Example**
- Comparing production machine consistency
- Rainfall predictions
- Stock price fluctuations
- Delivery time variations
- Height/weight deviations
- Daily temperature changes.


**Chernoff**: Comparing yes/no choices, two possible outcomes (success/failure)  [Good when very far from expectation]
**Example**
- Comparing marketing methods (click/no click)
- Coin flip (heads/tails)
- Baby birth (male/female)
- Product QC (defect/good)
- Buyer checkout (buy/not)
- Email marketing (opened/not)
- Patient recovery (yes/no)
- Game win (win/lose)
- Flight on-time (yes/no)
- Rain today (yes/no). 

**Concentration Applications**
1. Figure out what could possibly go wrong -- often these are dependent
2. Use a concentration inequality for each of the things that could go wrong.
3. Union bound over everything that could go wrong.

#### Real-World Example -- Privacy Preservation with Randomness
You’re working with a social scientist. They want to get accurate data on the rate at which people cheat on their romantic partners. 
We know about polling accuracy! Do a poll, call up a random sample of adults and ask them “have you ever cheated on your romantic partner?” 

Use a tail-bound to estimate the needed number $n$ get a guaranteed good estimate, right? You do that, and somehow, no one says they cheated... weird... right?

**What's the problem?**
Why would I want someone to know if I cheated and for them to publish that data on a public journal. Also, if you're on the researcher's side and you have the data of this, you could face some problems. Databases can be leaked, infiltrated, or subpoenaed. No one wants this data!

**So how do we fix this**
We don't really need to know who was cheating, we just care about how many people cheated. 
This is how we design our experiment: [good thing is that if your data ever gets leaked no one knows if you flipped heads or if you cheated]
- Please flip a coin
- If the coin is heads, or if you have ever cheated, tell me "heads" [how do we calculate the probability?]
- If the coin is tails and you have not ever cheated, tell me "tails"

You discovered that someone said heads, what's the probability that they cheated?

$$P(C | H) = \frac{1 \cdot P(C)}{\frac{1}{2} P(\bar{C}) + 1 \cdot P(C)}$$
This depends on the "prior" probability, which is $P(H | C)$, the updated probability is $P(C | H)$.

Real estimate: 20% of married individuals cheat on their partners????

**How does this relate to tail bounds?** 
It shall be revealed later.

Suppose you asked 100 people the "heads/tails" question, and 60 people said "heads". We expect that 50 of these people will flip a heads, so there's a high chance that 10 of these people are lying. 

BUT NO!!! VICKY YOURE WRONG!!!!!
Since our experiment is basically asking the person "is the flip heads or tails" if they flip heads, we're cutting down the number of people we asked the "cheat/not cheat" question in half. So, there's a chance that 10 people cheated, times two, which is roughly 20 people that cheat. 

Here's why:
Suppose you poll $n$ people and let $X$ be the numebr of people who said heads. We'll find an estmiate $Y$ of the number of peopl who cheated in the sample, and let $p$ bet he true probability of cheating in the population. What shoudl $Y$ be? Can we draw a margin of error around $Y$?

$P(X_{i = 1}) = \frac{1}{2} + \frac{1}{2} \cdot p$
$E[X] = \frac{n}{2} + \frac{1}{2} E[Y]$, where E[Y] is the numebr of epople who were really cheating
We define $Y$ to be: $Y = 2\left( X - \frac{n}{2} \right)$ [X - n/2 is the "extra" number of heads] 

**What's the variance of Y? Can I use a tail bound to figure out how close Y is to the expectation?**
We can use the Chernoff bound -- it has the strongest assumption so it has the strongest bound (as of the tools we have now)
-> but... we can't bound $\delta$ without bounding $p$.

#### Hoeffding's Inequality
> Let $X_{i}, X_{2}, \dots, X_{n}$ be independent RVs, each with range $[0, 1]$. Let $\bar{X} = \sum \frac{X_{i}}{n}$, and $\mu = \mathbb{E}[\bar{X}]$. For any $t \geq 0$
> 
> [write it here] 


$t$ in Hoeffding's Inequality is the margin of error. 

**Back to the original problem**
We lose a factor of two in the length of the margin. We need to talk to 4 times the number of people to have the same confidence interval as if I had just ran a regular poll. However, we can still control this tradeoff:
- More accuracy? Make them roll a die and report a 1 if they cheated
- More security? Make it Bernoulli with probability $p > \frac{1}{2}$ or cheated [like... "die roll 1 and didn't cheat" or "die roll 2-6" or did cheat]

**But will people understand this and will the experiment be accurate?**
YES! they will. 

Interesting thing to read where a UW person actually used this method: [Ask Me Anything | Proceedings of the 51st ACM Technical Symposium on Computer Science Education](https://dl.acm.org/doi/10.1145/3328778.3372658)



---
Back to: [[CSE 312 A - Class Details]]

#ComputerScience