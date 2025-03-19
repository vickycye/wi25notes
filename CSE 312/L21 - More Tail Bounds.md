28 February 2025

---
### Quick notes
- 

### To do
- [ ] Concept check
- [ ] Start homework 7
- [ ] Review section solutions from yesterday

---
## Lecture Recording Notes

- Union Bounds

### Concept Check 
**Question 1**
>Let G be a random graph with nn nodes. In a "random graph", each (unordered) pair of nodes can be connected with an (undirected) edge with probability $p$. For arbitrary nodes: $a,b,c,d$ in the graph, the event $\{a,b\}$ are connected is independent of the event $\{c,d\}$ are connected, whenever $\{a,b\} \neq \{c,d\}$
>
>You can imagine the graph to be a social network with $n$ people, in which each pair of people can be friends at random with probability $p$. The event of a particular pair $\{a,b\}$ being friends is independent of other pairs of people being friends (including pairs involving just one of $a$ or $b$).
>
>Given $n=7,p=\frac{1}{3}$​. Use union bound to give an upper bound of the probability of the event: there exists a node that is not connected with any other node.
>
>(Give your answer to the 4th decimal number)

Reasoning: We calculate the union bound which is the probably of all the events happening either at the same time or not (union).
So we have $$\bigcup_{i = 1}^{n} N_{i} \text{, where $N_{i}$ is the event where the ith person is not friends with anyone else}$$
We have $P(N_{i}) = \left( 1 - \frac{1}{3} \right)^{7 - 1}$, following $P(N_{i}) = \left( 1 - p \right)^{n - 1}$

So, by the Union bound, we have $$\mathbb{P}(N) = \mathbb{P}\left( \bigcup_{i = 1}^{n} N_{i} \right) \leq \sum_{i} \mathbb{P}(N_{i})$$
and we have $7 * \left( \frac{2}{3} \right)^{6} \approx 0.6145$

**Question 2**



---
Back to: [[CSE 312 A - Class Details]]

#ComputerScience