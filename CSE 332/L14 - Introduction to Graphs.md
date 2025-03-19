11 February 2025

---
### Quick notes
- 

### To do
- [ ] Practice exams for STAT 311
- [ ] EX06 on Gradescope

---
## Lecture Notes

A graph is "strongly connected" if every vertex can get to another vertex
A complete and fully connected graph has an edge from every vertex to every other vertex.

![[types_of_graphs.png]]

#### Directed Acyclic Graphs (DAGs)
- Directed graph with no directed cycles
- Every rooted directed tree is a DAG
- Every DAG is a directed graph
	- But not every directed graph is a DAG

### What is the Data Structure?
##### Adjacency Matrix
- Assign each node a number from $0$ to $\lvert V \rvert - 1$ 
- A $\lvert V \rvert \times \lvert V \rvert$ matrix of booleans, so if there is a connection between two vertices, that place in the matrix gets marked as `true`.
##### Adjacency List
- Assign each node a number from $0$ to $\lvert V \rvert - 1$ 
- An array of length $\lvert V \rvert$ where each entry stores a linked list of all adjacent vertices

| Property                   | Adjacency Matrix | Adjacency List             |
| -------------------------- | ---------------- | -------------------------- |
| Get a vertex's out-edges   | $O(V)$           | $O(d)$ [for printing them] |
| Get a vertex's in-edges    | $O(V)$           | $O(V + E)$                 |
| Decide if some edge exists | $O(1)$           | $O(d)$                     |
| Insert an edge             | $O(1)$           | $O(d)$ [check for dupes]   |
| Delete an edge             | $O(1)$           | $O(d)$ [find it first]     |
| Space                      | $O(V^2)$         | $O(V + E)$                 |
| Sparse or Dense Graph?     | Dense graph      | Sparse Graph               |
Inserting an edge for adjacency list can also be $O(1)$ if we don't need to check if the edge already exists

So, if there's a space requirement and the graph is sparse, we can use an adjacency list.


---
Back to: [[CSE 332 A - Class Details]]

#ComputerScience