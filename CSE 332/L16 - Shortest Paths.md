14 February 2025

---
### Quick notes
- EX08 will not be a programming one

### To do
- [ ] EX07 due next monday 2/24
- [ ] read about parallelism on the course webpage?

---
## Lecture Notes

For shortest path, BFS doesn't necessarily work because the shortest path may not have the fewest edges. Assume no negative weights. 
- If there are negative weights, there might be negative cycles 

### Dijkstra's Algorithm
- Handles weights, growing the set of nodes whose shortest distance has been computed
- Nodes not in the set will have a "best distance so far"
- A PQ will be used for best efficiency

Dijkstras is like League of Legends because there is fog of war 

How it works:
- Start node has cost - and all other nodes have cost $\infty$
- At each step, pick the closest unknown vertex $v$ and add it to the "cloud" of known vertices, then update distances for nodes with edges from $v$. 

[DSA Dijkstra's Algorithm](https://www.w3schools.com/dsa/dsa_algo_graphs_dijkstra.php#:~:text=Dijkstra's%20algorithm%20finds%20the%20shortest,all%20the%20unvisited%20neighboring%20vertices.)

For undirected graphs: [Dijkstra's Algorithm Visualizer - by Jan S.](https://www.davbyjan.com/)

**The "known" Cloud**
Suppose $v$ is the next node to be marked as known, the best known path to v must have only nodes in the "known cloud"
- We only know about paths through the cloud to a node right outside the clodu

If the actual shortest path to v is different, it won't only use cloud nodes. Let w be the frist non cloud node on this path -> path up to w is already known and must be shorter than the best-known path to v. So v would not have been picked. [This is not possible, so it is always the shortest path in the known cloud]

### Greedy Algorithms
- At each step in a greedy algorithm, it does what it seems to be best at that point
- Once a vertex is known, it si not revisited, but it turns out to be globally optimal




---
Back to: [[CSE 332 A - Class Details]]

#ComputerScience