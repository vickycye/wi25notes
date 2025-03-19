11 March 2025

---
### Quick notes
- Missed this class-- I was in ZoomCare. lolz
- Some problems in EXP seem easier. For example, for Hamiltonian path, it's "hard" to look at a graph and determine whether it has a Hamiltonian path, but it's "easy" to verify if a given path is a Hamiltonian path or not.

### To do
- [ ] EX11 [Extended to Friday]
- [ ] Finals prep -- material on class calendar already

---
## Lecture Notes

**Examining Running Times**
Polynomial times: $O(1), O(\log n), O(n), O(n \log n), O(n^2)$, etc.
Exponential times: $O(2^n)$, etc.
Superexponential functions: $n!$ [still in exponential] $n! \in O(2^n)$

| Size of $n$     | $n$     | $n \log n$ | $n^2$                                             | $n^3$                                                  | $1.5^n$                                                | $2^n$                                                 | $n!$                                                  |
| --------------- | ------- | ---------- | ------------------------------------------------- | ------------------------------------------------------ | ------------------------------------------------------ | ----------------------------------------------------- | ----------------------------------------------------- |
| $n = 10$        | < 1 sec | < 1 sec    | < 1 sec                                           | < 1 sec                                                | < 1 sec                                                | < 1 sec                                               | 4 sec                                                 |
| $n = 30$        | < 1 sec | < 1 sec    | < 1 sec                                           | < 1 sec                                                | < 1 sec                                                | <span style="color:rgb(255, 0, 0)">18 mins</span>     | <span style="color:rgb(255, 0, 0)">10^25 years</span> |
| $n = 50$        | < 1 sec | < 1 sec    | < 1 sec                                           | < 1 sec                                                | <span style="color:rgb(255, 0, 0)">11 mins</span>      | <span style="color:rgb(255, 0, 0)">36 years</span>    | <span style="color:rgb(255, 0, 0)">very long</span>   |
| $n = 100$       | < 1 sec | < 1 sec    | < 1 sec                                           | 1 sec                                                  | <span style="color:rgb(255, 0, 0)">12,892 years</span> | <span style="color:rgb(255, 0, 0)">10^17 years</span> | <span style="color:rgb(255, 0, 0)">very long</span>   |
| $n = 1,000$     | < 1 sec | < 1 sec    | 1 sec                                             | <span style="color:rgb(255, 0, 0)">18 mins</span>      | <span style="color:rgb(255, 0, 0)">very long</span>    | <span style="color:rgb(255, 0, 0)">very long</span>   | <span style="color:rgb(255, 0, 0)">very long</span>   |
| $n = 10,000$    | < 1 sec | < 1 sec    | 2 min                                             | <span style="color:rgb(255, 0, 0)">12 days</span>      | <span style="color:rgb(255, 0, 0)">very long</span>    | <span style="color:rgb(255, 0, 0)">very long</span>   | <span style="color:rgb(255, 0, 0)">very long</span>   |
| $n = 100,000$   | < 1 sec | 2 sec      | <span style="color:rgb(255, 0, 0)">3 hours</span> | <span style="color:rgb(255, 0, 0)">32 years</span>     | <span style="color:rgb(255, 0, 0)">very long</span>    | <span style="color:rgb(255, 0, 0)">very long</span>   | <span style="color:rgb(255, 0, 0)">very long</span>   |
| $n = 1,000,000$ | 1 sec   | 20 sec     | <span style="color:rgb(255, 0, 0)">12 days</span> | <span style="color:rgb(255, 0, 0)">31,710 years</span> | <span style="color:rgb(255, 0, 0)">very long</span>    | <span style="color:rgb(255, 0, 0)">very long</span>   | <span style="color:rgb(255, 0, 0)">very long</span>   |
Talk about a lot of time... we're gonna look at some algorithms that can solve the problems on this -> side [past n-cubed]

<mark style="background: #FFF3A3A6;">Tractable</mark> means feasible to solve in the "real-world"
<mark style="background: #FFF3A3A6;">Intractable</mark> means infeasible to solve in the "real-world"

- For ML, tractable might be $O(n)$ or $O( \log n)$, but for most applications it's either $O(n^3)$ or $O(n^2)$
- Most natural problems can only be solved with small-degree polynomials, or otherwise it has to be solved with an exponential time. [It's rare to have a running time of n^5, for example.]


### Euler Path Problem
Here's the definition of a regular path: A sequence of nodes such that for every consecutive pair are connected by an edge. 

**Euler's Path**: A path such that every edge in the graph appears exactly once. 
- In general, if a graph has at most 2 vertices [either 0 or 2] with an odd degree and everything else has an even degree, and Euler's path exists. 

**Hamiltonian Path**: A path that includes every node in the graph exactly once $O(2^n)$

### Complexity Classes
In computational complexity theory, a complexity class is a set of computational problems "of related resource-based complexity". The two most commonly analyzed resources are time and memory.

![[complexity_classes.png]]
#### Complexity class P -- "Polynomial"
- The set of problem which have an algorithm whose running time is $O(n^p)$ for some choice of $p \in \mathbb{R}$
- We say problems belonging to $P$ as tractable.
- $P \in EXP$

#### Complexity class EXP - "Exponential"
- The set of problems which have an algorithm whose running time is $O(2^{n^p})$ for some choice of $p \in \mathbb{R}$
- We say all problems in $EXP$ are intractable. 
- This is really all problems outside the $P$ class--but there are still several problems that don't belong in neither $P$ or $EXP$. 

![[EXP and P.png]]

Examples:

| P - Tractable | EXP - Intractable          | NP [More explained later] |
| ------------- | -------------------------- | ------------------------- |
| Sorting       | Hamiltonian Path           | Checkers                  |
| Shortest Path | Longest path               | Go                        |
| Euler's Path  | Vertex cover               | Chess                     |
|               | Independent Set            |                           |
|               | Satisfiability             |                           |
|               | Most Board Game Strategies |                           |

The goal for each problem is to either: find an efficient algorithm if it exists (belongs to P), or find out that there is no efficient algorithm (doesn't belong to P). It might be easier to show that a problem belongs to $C$ instead of $P$, so showing $C \subseteq P$ might be useful.

### So wtf is NP then...?

It's not being able to solve a problem, but being able to verify if the solution you gave me is a valid solution.

#### Complexity class NP - "Non-deterministic polynomial"
The set of problems for which a candidate solution can be verified in polynomial time. 
- $P \subseteq NP$
- Corresponds to algorithms that can guess a solution (if it exists), which is then verified to be in polynomial time.

![[p_np_exp.png]]

#### NP-Complete
- A set of "together they stand, together they fall" problems
- The problems in this set either all belong in $P$, or none of them do. [Intuitively, the hardest problems in NP]
- Collection of problems from $NP$ that can all be "transformed" to each other in polynomial time. For example, a "vertex cover" problem can be transformed into a "Hamiltonian path" problem.

![[final_p_equals_np_chart.png]]

#### NP-Hard
- How can we figure out if $P = NP$?
- We first find out if a problem is at least as "hard" as $NP$. 
- If any of these problems can be solved in $P$ time, then all $NP$ problems can be solved in $P$ time. E
- $B$ is NP-Hard if EVERY problem within NP reduces to $B$ in polynomial time. 
- [Chess? Halting problem?]



---
Back to: [[CSE 332 A - Class Details]]

#ComputerScience