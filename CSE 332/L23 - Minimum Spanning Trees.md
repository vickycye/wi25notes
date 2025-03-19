5 March 2025

---
### Quick notes
- Not dropping EX12 [No P, NP, NP-Complete on the final exam]

### To do
- [ ] Check EX10 with people 

---
## Lecture Notes

A tree is a graph that is undirected, acyclic, and connected [Review]
How many edges are in a tree? **E** -> **V - 1**

A minimum spanning tree is a graph where it's still a tree (undirected, acyclic, and connected), but the sum of the cost of every single edge is minimal.

![[minimum_spanning_tree.png]]

Both Prim's and Kruskal's are greedy algorithms -> they don't go back and reconsider their choices

![[prims_kruskals.png]]

### Prim's Algorithm - Node based
- Almost identical to Dijkstra's
- One node, grow greedily
Idea: grow a tree by picking a vertex from the unknown set that has the smallest cost where the cost is the distance from the known set.

Data structure: Priority Queue [min heap], Adjacency list [graph representation]

1. For each node `v`, set `v.cost = infinity` and `v.known = false`.
2. Choose any node `v` which is like the start vertex in Dijkstra
	1. Mark `v` as known
	2. For each edge `(v, u)` with weight `w`, set `u.cost = w` and `u.prev = v`
3. While there are unknown parts in the graph 
	1. Select the unknown node `v` with the lowest cost
	2. Mark `v` as known and add `(v, v.prev)` to output the MST
	3. For each edge `(v, u)` with weight `w`, where `u` is unknown:
	
		if (w < u.cost) {
			u.cost = w;
			u.prev = v;
		}

### Kruskal's Algorithm - Edge based
- Forest of MSTs, union them together [need a new data structure]
- [Disjoint Set Data Structures - GeeksforGeeks](https://www.geeksforgeeks.org/disjoint-set-data-structures/)
Idea: grow a forest out of edges that do not create a cycle. Pick an edge with the smallest weight. 

Data structure: Priority Queue for edges, Disjoint set [union find]

1. Initialize with 
	1. Empty MST
	2. All vertices marked unconnected
	3. All edges unmarked
2. While all vertices are not connected
	1. Pick the lowest cost edge `(u, v)` and mark it
	2. If `u` and `v` are not already connected, add `(u, v)` to the MST and mark `u` and `v` as connected to each other.

### Disjoint Set ADT
[covered on Friday]

---
Back to: [[CSE 332 A - Class Details]]

#ComputerScience