24 January 2025

---
### Quick notes
- Can think of conditional probability intuition by thinking if an event is more likely to happen if you were given additional information.
- You have to check all subsets to make sure if events are mutually independent. For example, if you roll a dice and there are 3 events, the 3 events might be mutually independent, but a pair might not be. 

### To do
- [ ] Start homework 3
- [ ] Write notes sheet for quiz on Thursday
- [ ] Start preparing for quiz on Thursday


---
## Lecture Notes

- It's easier to visualize conditional probability in a probability tree [good for small branching factors]


### Pairwise and Mutual Independence

Independence for three or more events

**Pairwise Independence**
>Events $A_1, A_2, \cdots, A_n$ are pairwise independent if for all $i, j$, $\mathbb{P}(A_1 \cap A_j) = \mathbb{P}(A_1) \cdot \mathbb{P}(A_j)$

**Mutual Independence**
- No matter what subset of events you look at, the subset still has the independence property
>Events $A_1, A_2, \cdots, A_n$ are mutually independent if $\mathbb{P}(A_1 \cap A_j \cap \cdots \cap A_{i_k}) = \mathbb{P}(A_{i_1}) \cdot \mathbb{P}(A_{i_2}) \cdots \mathbb{P}(A_{j_k})$ for every subset $\{i_1, i_2, \cdots i_k\}$ of $\{1, 2, \cdots, n\}$


**Example**
If we roll two fair dice (one red one blue) independently, are the events pairwise independent or mutually independent?

**Testing for pairwise independent**
R = P(roll a red 3)
B = P(roll a blue 5)
S = P(sum is 7)

P(R and B) = P(R) P(B) -> Yes, also by the problem statement
P(R and S) = P(R) P(S) -> Yes
P(B and S) = P(B) P(S) -> Yes

Since all three pairs are independent, we say the random variables are <span style="color:rgb(255, 192, 0)">pairwise independen</span><span style="color:rgb(255, 192, 0)">t</span>.

**Testing for mutually independent**
P(R and B and S) = 0; if the red die is 3, the blue die is 5, then there is no way the sum is 7.
P(R) P(B) P(S) = 1/216.
The two are not equal, so they are not <span style="color:rgb(255, 192, 0)">mutually independent</span>.

<mark style="background: #FFB8EBA6;">If something is mutually independent, then it must be pairwise independent as well!</mark>


### Applications of The Above

1. Helping doctors and patients make sense of health statistics

P(has disease) = 0.01
P(tests positive | has disease) = 0.90
P(test positive | no disease) = 0.09

P(positive), what the chances of having the disease?

P(has disease | positive) = P(positive | has disease) * P(has disease) / P(positive)
					= 0.90 * 0.01 /  0.90 * 0.01 + 0.09 * 0.99
					= ~ 0.0917

P(positive) = P(positive | disease) * P(disease) + P(positive | no disease) * P(no disease)
		= 0.90 * 0.01 + 0.09 * 0.99

C. out of 10 people with a positive test, about 1 have the disease




---
Back to: [[CSE 312 A - Class Details]]

#ComputerScience