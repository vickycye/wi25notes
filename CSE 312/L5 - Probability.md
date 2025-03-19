15 January 2025

---
### Quick notes
- Uniform measure - all cases are equally likely
- $\mathbb{P}(\omega)$ is omega
- A good indication if you're doing a problem correctly if your sample space is really large is if you cancelled a lot of terms in common between the numerator and the denominator
- Can use the corollaries as facts in the homework

### To do
- [x] Print homework 2 ✅ 2025-01-16
- [x] Start homework 2 ✅ 2025-01-16
- [x] Print Kat's waivers ✅ 2025-01-15
- [ ] Review the non-uniform-measure approach to the dice problem
- [x] Concept check 5 ✅ 2025-01-16
- [x] Add the discrete probability and conditional probability sections into the notebook ✅ 2025-01-16

---
## Lecture Examples

> Suppose you roll two dice. Each die is fair and they don't affect each other. What is the probability of both dice being even?

One approach:
**Sample space:** $\{1, 2, 3, 4, 5, 6\} \times \{1, 2, 3, 4, 5, 6\}$
**Probability measure:** $\mathbb{P}(\omega) = 1/36$ for all $\omega \in \Omega$
**Event**: $\{ 2, 4, 6 \} \times \{ 2, 4, 6\}$
**Probability:** $\frac{3^2}{6^2}$ [can leave as is in homework]

> Suppose you roll two dice. What if you can't tell them apart? What is the probability of both dice being even?

**Sample space:** $\{(1, 1), (1, 2), \cdots, (5, 6), (6, 6)\}$ [all 36 possible outcomes]
**Probability measure:** $\mathbb{P}((x, y)) = 2/36$ if $x \neq y$, $\mathbb{P}(x, x) = 1/36$  [can't be the uniform measure]
**Event:** $\{(2, 2), (4, 4), (6, 6), (2, 4), (2, 6), (4, 6)\}$
**Probability:** $3 \cdot \frac{1}{36} + 3 \cdot \frac{2}{36} = \frac{9}{36}$

> Suppose you shuffle a deck of cards so any arrangement is equally likely. What is the probability that the top two cards have the same value?

**Sample space**: $\{(x, y): x \text{ and } y \text{ are different cards}\}$ or set of all orderings of all 52 cards
**Probability measure:** $\mathbb{P}(\omega) = \frac{1}{52 \cdot 51}$ or $\mathbb{P}(\omega) = \frac{1}{52!}$
**Event:** all pairs with equal values or all lists that start with 2 cards of the same value
**Probability:** $\frac{13 \cdot P(4, 2)}{52 \cdot 51}$ or $\frac{13 \cdot P(4, 2) \cdot 50!}{52!}$, which evaluate to the same result

### Uniform Probability Space

In the uniform measure, for every event $E$, $\mathbb{P}(E) = \frac{\lvert E \rvert}{\lvert \Omega \rvert}$

[did a problem on the probability of there being exactly 50 heads in 100 coin tosses]

### Discrete Probability

$\mathbb{P}(E) = 0$ iff an event can't happen
$\mathbb{P}(E) = 1$ iff the event is guaranteed 

### Conditional Probability

Basically, "If I were to tell you some extra information, how would the probability change depending on that information?"
Definition: For an event $B$, with $\mathbb{P}(B) > 0$, the "Probability of $A$ conditioned on $B$" is 
$$\mathbb{P} (A \vert B) = \frac{\mathbb{P}(A \cap B)}{\mathbb{P}(B)}$$
`probability of A given B`

> If I were to roll a pair of dice, the the sum of the dice is 4, what is the chance that one of the die shows a 5?

The sample space has been restricted, therefore the chances of that happening is smaller. And, it's impossible to have a dice show a 5 and the sum be a 4. 

[friday we will do more examples]



---
Back to: [[CSE 312 A - Class Details]]

#ComputerScience #Stats 