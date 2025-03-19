7 March 2025

---
### Quick notes
- No need to worry about how Disjoint Set is implemented [in this class at least]
- Binomial queue / fibonacci heap
	- [courses.cs.washington.edu/courses/cse373/03au/lectures/binomialqueues.pdf](https://courses.cs.washington.edu/courses/cse373/03au/lectures/binomialqueues.pdf)
	- [Fibonacci heap - Wikipedia](https://en.wikipedia.org/wiki/Fibonacci_heap)

### To do
- [ ] EX11 [prims]
- [ ] EX12 [released sometime later]

---
## Lecture Notes

### Disjoint Set ADT & Union Find

Unioning the sets together is like connecting two trees in Kruskal's algorithm.  
`Union(x, y)` is `O(1)` worst case, since we're just joining two trees
`Find(x)` is `O(log n)` worst case since we're going through all levels of a heap

##### Disjoint Set ADT implementation
```
// Disjoint set data structure
class DSU {
    private int[] parent, rank;

    public DSU(int n) {
        parent = new int[n];
        rank = new int[n];
        for (int i = 0; i < n; i++) {
            parent[i] = i;
            rank[i] = 1;
        }
    }

    public int find(int i) {
        if (parent[i] != i) {
            parent[i] = find(parent[i]);
        }
        return parent[i];
    }

    public void union(int x, int y) {
        int s1 = find(x);
        int s2 = find(y);
        if (s1 != s2) {
            if (rank[s1] < rank[s2]) {
                parent[s1] = s2;
            } else if (rank[s1] > rank[s2]) {
                parent[s2] = s1;
            } else {
                parent[s2] = s1;
                rank[s1]++;
            }
        }
    }
}
```

##### Runtime
$O(|E| \log |E| + |E| \log |V|)$


### Topological Sort

Topological ordering respects the original graph relationship

Requires a DAG.

**First Algorithm for Topological Sort**
1. Label each vertex with its in-degree [could traverse through entire adjacency list]
2. While there are vertices that are still not outputted
	1. Choose a vertex `v` labeled with in-degree of 0
	2. Output `v` and conceptually remove it from the graph
	3. For each vertex `w` adjacent to `v`, decrement the in-degree of `w`.

The runtime for labelling each vertex with its in-degree is $O(|V| + |E|)$ since there could either be a greater number of vertices or edges. The graph doesn't have to be connected [unconnected segments would just have an in-degree of 0].

```java
labelEachVertexWithItsInDegree(); // O(V + E)
for (i = 0; i < numVertex; i++) { // V times
	v = findNewVertexOfDegreeZero(); // O(V)
	put v next in output // O(1)
	for each w adjacent to v // d times
		w.indegree--; // O(1)
}
// O((V + E) + V(V + 1 + d(1)))
// O(V + E + V^2 + V + E)
// O(V^2 + E)
```


**Optimised Topological Sort**

- Queue only contains vertices with in degree 0

```java
labelEachVertexWithItsInDegree(); // O(V + E)
for (i = 0; i < numVertex; i++) { // V times
	v = dequeue(); // O(1)
	put v next in output // O(1)
	for each w adjacent to v // d times
		w.indegree--; // O(1)
		if (w.indegree == 0) // O(1)
			enqueue(w); // O(1)
}
// O((V + E) + V(1 + 1 + d(1)))
// O(V + E + V + V + E)
// O(V + E)
```





---
Back to: [[CSE 332 A - Class Details]]

#ComputerScience