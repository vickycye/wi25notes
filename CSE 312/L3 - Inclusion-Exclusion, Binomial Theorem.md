10 January 2025

---
### Quick notes
- Giving a "combinatorial argument" means giving at least 2 ways to solve a problem which make sense together.

### To do
- Submit Homework 1 on Gradescope
- Write lecture in notebook

---
## Lecture Notes

#### Proof by Double-Counting / Combinatorial Proof

### Pascal's Rule

${n \choose k} = {n - 1 \choose k - 1} + {n - 1 \choose k}$
basically means adding two disjoint sets that will sum up to the original set of people.
${n - 1 \choose k - 1}$ In this case, we're on the team, and we're choosing other people to be on the team, minus 1 because I'm already in the team (we're in the "universe")
${n - 1 \choose k}$ In this case, we're not on the team, so we're choosing a total of k people to be on the team (we're not in the "universe")

[Review this slide in the lecture again]


### Binomial Theorem

>$$(x + y)^n = \sum_{i = 0}^{n} {n \choose i} x^i y^{n - i}$$


### Principle of Inclusion-Exclusion

- We're taking two sets that are intersected, so if we count it normally, we would **overcount**.
- If it were two disjoint sets, we would just use the Sum Rule and add them together

Two sets:
$$\lvert A \cup B \rvert = \lvert A \rvert + \lvert B \rvert - \lvert A \cap B \rvert$$
Three sets:
$$\lvert A \cup B \rvert = \lvert A \rvert + \lvert B \rvert + \lvert C \rvert - \lvert A \cap B \rvert - \lvert B \cap C \rvert - \lvert A \cap C \rvert + \lvert A \cap B \cap C \rvert$$




---
Back to: [[CSE 312 A - Class Details]]

#ComputerScience #Stats 