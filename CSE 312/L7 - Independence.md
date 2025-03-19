22 January 2025

---
### Quick notes
- Quiz next Thursday
- When talking about conditional probability, even if the events are independent themselves, if you have two events that involve overlapping events, then they may be dependent.
- Read a problem carefully-- when we say "these steps are independent of each other" about some part of a sequential process, it's usually conditioned on all prior steps, these steps are conditionally independent of each other. 

### From Homework Review
- 1b) its like choosing members for a swim team and then choosing swim captains
- Include sum rule and product rule on Problem 1 in 312 homework
- 

### To do
- [ ] Concept check 8
- [ ] Print homework 3
- [ ] Start homework 3
- [ ] Move lecture notes to notebook -- start on Chain Rule
- [ ] Find section from last week and put it in obsidian notes
- [ ] MUST DO WANG RESEARCH MEETING STUFF BY TOMORROW 🔺 

---
## Lecture Notes

##### Independence
> Two events, $A, B$ are independent if $\mathbb{P}(A \cap B) = \mathbb{P}(A) \cdot \mathbb{P}(B)$

Are the following events independent?
1. We flip c fair coin three times. Each flip is independent. Is $E = \{ HHH \}$ independent of $F$ = "at most two heads"? -> Not independent
	- $\mathbb{P} (E \cap F) = 0$ [you cannot have three heads and at most two heads]
	- $\mathbb{P} = 1/8, \mathbb{P}(F) = 7/8, \mathbb{P}(E \cap F) \neq \mathbb{P}(E) \mathbb{P}(F)$
	- [If one event happened and you knew about it, then you change your opinion on something else didn't happen, that means its a conditional probability]
1. Are $A$ = "the first flip is heads" and $B$ = "the second flip is tails" -> Independent
	- $\mathbb{P}(A \cap B) = 2/8$ [there is uniform measure]
	- $\mathbb{P}(A) = 1/2, \mathbb{P}(B) = 1/2; \frac{2}{8} = \frac{1}{2} \cdot \frac{1}{2}$. 

### Chain Rule

>The chain rule states that $\mathbb{P}(A_1 \cap A_2 \cap \cdots \cap A_n) = \mathbb{P}(A_n \vert A_1 \cap \cdots \cap A_{n - 1}) \cdot \mathbb{P}(A_{n - 1} \vert A_1 \cap \cdots \cap A_{n - 2}) \cdots \mathbb{P}(A_2 \vert A_1) \cdot \mathbb{P}(A_1)$

**Example**
You shuffle a standard deck of 52 cards so every ordering is equally likely.
- Let $A$ be the event that the top card is a K ♦️
- Let $B$ be the event that the second card is a J ♠️
- Let $C$ be the event that the third card is a 5 ♠️

What is $\mathbb{P}(A \cap B \cap C)$?
We use the chain rule and get: $\mathbb{P}(A) \cdot \mathbb{P}(B \vert A) \cdot \mathbb{P}(C \vert A \cap B)$ = $\frac{1}{52} \cdot \frac{1}{51} \cdot \frac{1}{50}$. 

### Conditional Independence
>We say $A$ and $B$ are conditionally independent on $C$ if
>$\mathbb{P}(A \cap B \vert C) = \mathbb{P}(A \vert C) \cdot \mathbb{P}(B \vert C)$

**Example**
You have two coins. Coin $A$ is fair, coin$B$ comes up with heads with probability 0.85. You will roll a fair die, if the result is odd flip coin $A$ twice (independently); if the result is even flip coin $B$ twice (independently).

Let $C_1$ be the event that the first flip is heads and $C_2$ be that the second flip is heads. $O$ is the event that the die was odd. 

Are $C_1$ and $C_2$ independent?
- If you know the die roll, the coin flips are independent. If you didn't know the die roll, and you flip a coin but there are more occurrences of heads, then its more likely for the events to be dependent since it's likely to be coin $B$. 
- [it might be easier to think of this problem for Coin A always being tails, and Coin B always being heads. With these extreme conditions, you would know which coin is being flipped, and therefore you know the result of the die roll]

### More Bayes' Practice

**Example**
You have three red marbles and one blue marble in your left pocket, and one red marble and two blue marbles in your right pocket. 

You will flip a fair coin; if it's heads, you'll draw a marble from your left pocket, if it's tails you'll draw a marble from your right pocket

Let $B$ be you draw a blue marble. Let $B$ be the coin is tails.

What is $\mathbb{P}(B \vert T)$ and what is $\mathbb{P}(T \vert B)$?

**Solution**
$\mathbb{P}(T \vert B) = \frac{\mathbb{P}(B \vert T) \cdot \mathbb{P}(T)}{\mathbb{P}(B)} = \frac{\frac{2}{3} \cdot \frac{1}{2}}{\frac{3}{7}} = \frac{7}{9}$
Thus, the probability is greater than 0.5.


### Technical Notes
After you condition on an event, what remains is another probability space. 
With $B$ playing the role of the sample space, $\mathbb{P}(\omega \vert B)$ playing the role of the probability measure.
-> The complementary law still exists, and Bayes' theorem also exists. 

---
Back to: [[CSE 312 A - Class Details]]

#ComputerScience