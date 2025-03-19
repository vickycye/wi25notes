12 February 2025

---
### Quick notes
- Two more exercises coming out [graph implementation exercises / traversal exercise?]
- For visualization DFS and BFS: [Graph Traversal (Depth/Breadth First Search) - VisuAlgo](https://visualgo.net/en/dfsbfs)
- 

### To do
- [ ] Finish EX06 🔺 
- [ ] Print practice exams for STAT 311
- [ ] DO STAT 311 PRACTICE PROBLEMS DUE ON THE 19TH!! 🔺 
- [ ] Concept check 15 for CSE 312 🔺 

---
## Lecture Notes

- Mark nodes after visiting them, can use `boolean[] visited` or something of the sort to keep track

Average traversal pseudocode
1. create a data structure to "track" nodes as visited or not
2. While the data structure is not empty, check for more
3. Add to visited every time you reach a new node

Assume all add and remove are $O(1)$, entire traversal is $O(\lvert E \rvert)$
### Breadth-First Search (BFS)
- Queue, since FIFO
>Explore areas closer to the start node first

"Level-order" traversal

```java
BFS(Node start) {
	// initialize q as a queue to hold start
	mark start as "visited"
	while (q is not empty)
		next = q.dequeue()
		// for each Node u adjacent to next
		if (u is not marked)
			// BFS(u)
			mark u and enqueue into q
}
```

[Breadth First Search or BFS for a Graph - GeeksforGeeks](https://www.geeksforgeeks.org/breadth-first-search-or-bfs-for-a-graph/)

Pros:
- Always finds shortest path

### Depth-First Search (DFS)
- Stack, because FILO
> Recursively explore one part before going back to the other parts not yet explored

```java
DFS(Node start) {
	// mark and process start
	mark start as "visited"
	// for each Node u adjacent to start
	while (s is not empty)
		next = s.pop()
		// if u is not marked
		if (u is not marked)
			// DFS(u)
			mark u and push onto s
}
```

[Depth First Search or DFS for a Graph - GeeksforGeeks](https://www.geeksforgeeks.org/depth-first-search-or-dfs-for-a-graph/)

Pros:
- Uses less space to find a path

### Iterative-Deepening Depth-First Search (IDDFS)

>**IDDFS** combines depth-first search’s space-efficiency and breadth-first search’s fast search (for nodes closer to root).

Basically, it recursively searches by "depth" through the entire graph. Starting from level 0, it performs a DFS and returns the values all the way up to level $d$. Once the goal is found, we quit [effectively not searching the entire graph]. -> Ensures that shallower nodes are visited first (BFS) while maintaining low memory usage (DFS).

More on IDDFS: [Iterative Deepening Search(IDS) or Iterative Deepening Depth First Search(IDDFS) - GeeksforGeeks](https://www.geeksforgeeks.org/iterative-deepening-searchids-iterative-deepening-depth-first-searchiddfs/)

Branching factor: $b$, depth: $d$
![[dfs_bfs_iddfs.png]]

Applications:
1. **Unbounded Search Spaces** -- depth of the solution is unknown, IDDFS prevents excessive memory usage compared to BFS.
2. **Optimal Pathfinding** -- if the cost per step is uniform, IDDFS finds the shallowest goal node first, making sure it's the most "optimal" path like BFS.
3. **AI and Game Trees** -- chess or puzzle solving where the exact solution depth is not known

### Other
- If we want to output the actual path instead of just finding the path, instead of marking a node "visited", we can store the node along the path. 



---
Back to: [[CSE 332 A - Class Details]]

#ComputerScience