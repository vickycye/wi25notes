22 January 2025

---
### Quick notes
- Review recurrence relationships because I kinda forgot most of it
- Recurrence Relationship for section review tomorrow

### To do
- [ ] Must finish EX02 - Heaps [asking for big O bounds in homework?]
- [ ] Start EX03 - Recurrences

---
## Lecture Notes

### Review on Recurrence Relationships
- Draw the trees out and figure out the work per level

For $T(n) = a T(\frac{n}{b}) + f(n)$
- The value of a is important
- The value of b is important
- The asymptotic analysis of $f(n)$ is also important

### Dictionaries and Trees

So far we've learned Stacks, Queues, and Priority Queues. Now, we're moving onto <span style="color:rgb(255, 192, 0)">DICTIONARIES!!!!</span> (aka Maps)
- sets of key, value pairs [keys often must be comparable]

We've also learned about this a little in [[L8 - HashMaps]] from [[CS 211 - Class Details]]

Operations:
- `insert(key, val)`: places a key, value pair in the map, if the key is already used, it overwrites the existing entry
- `find(key)`: returns the value associated with the key
- `delete(key)`: deletes the key and the value associated with it.

Applications of dictionaries:
1. Networks -> router tables
2. OS -> page tables
3. Compilers -> symbol tables
4. Databases -> dictionaries with other nice properties
5. Search -> inverted indices, phone directories...
6. Biology -> genome maps [i did not know this]

### Implementation details
- think about the worst case
- assume arrays have enough space
- keys cannot be duplicates

[assume all values in the table are Big Theta and not Big O]

|                              | `insert`    | `find`      | `delete`    |
| ---------------------------- | ----------- | ----------- | ----------- |
| Unsorted linked-list         | $\Theta(n)$ | $O(n)$      | $O(n)$      |
| Unsorted array               | $O(n)$      | $O(n)$      | $O(n)$      |
| Sorted linked list           | $O(n)$      | $O(n)$      | $O(n)$      |
| Sorted array [binary search] | $O(n)$      | $O(\log n)$ | $O(n)$      |
| Binary Search Tree [a line]  | $O(n)$      | $O(n)$      | $O(n)$      |
| Balanced Binary Search Tree  | $O(\log n)$ | $O(\log n)$ | $O(\log n)$ |
- unsorted linked list and unsorted array insert are both $O(n)$ because you have to traverse the array to make sure the same key isn't there
- sorted array insert operation is not log n because you have to shift all the elements over

### Lazy Deletion
- We want to make delete as fast as find [in a sorted array]
- Instead of actually removing the elements, we mark them as deleted [no need to shift values]

Pros:
- Simple
- Can do removals later in batches
- If re-added soon thereafter, unmark the deletion

Cons:
- Extra space for the 'deleted' flag
- Data structure full of deleted nodes wastes space
- `find` has $O (\log m)$ time where m is data-structure size ($m \geq n$)
- May complicate other operations

Applications? [from GPT]
- Hash Tables -> used to avoid rehashing and ensure proper handling of collisions during lookups.
- BSTs -> instead of re-balancing the tree immediately, nodes are marked as delete to allow for future updates [really?]
- Databases -> stored values are soft-deleted, until you "permanently delete it" [kinda like iphone photos]

Sources:
• Weiss, Mark Allen. _Data Structures and Algorithm Analysis in C++._
• Cormen, Thomas H., et al. _Introduction to Algorithms._

### Binary Tree Implementation
Structure
- Either empty, or has a
- Root, left subtree (can be empty), right subtree (can be empty)

For a binary tree of height $h$: [remember we did this in 311, also root node has height 0]
- max # of leaves: $2^h$
- max # of nodes: $2^{h + 1} - 1$
- min # of leaves: $1$ [has the single line structure]
- min # of nodes: $h + 1$ [also single line structure]

#### Calculating height
```
// we care about the height of the children
// recursively handling height calculation

int treeHeight(Node root) {
	if root is null return -1;
	return 1 + max(treeHeight(left child), treeHeight(right child));
}
```

### Traversals
- pre-order: root, left, right
- in-order: left, root, right
- post-order: left, right, root

[more slides on how traversal implementations and how recursive find works]

### Properties
Structure:
- each node has $\leq 2$ children
Order:
- all keys in left subtree are $\leq$ node's key
- all keys in right subtree are $\geq$ node's key

### Insert
1. find
2. create new node

### Delete
- if it's a leaf, just delete
- if it's a root to one child, just reroute the root's parent to it's child
- if it's a root to a subtree:
	1. replace deleted key with the [take a look at slides]


---
Back to: [[CSE 332 A - Class Details]]

#ComputerScience