24 January 2025

---
### Quick notes
- AVL is a BST
- We could get to an invalid AVL tree from a valid AVL tree by inserting an element that "attaches" to the lowest leaf nodes.

### To do
- [ ] Finish EX03
- [ ] Start EX04?

---
## Lecture Notes

In a dictionary that's implemented by a Binary Search Tree, when we call the `delete(key)` function, we replace that node with either the largest leaf of the smaller subtree, or the smallest leaf of the right subtree.

How to find the smallest or the largest -> 

Potential Balance Conditions [BUT THEYRE ALL WRONG!!!]
1. L and R subtrees of the root have equal number of nodes -> NO!!! This leads to a mess (tree & chain)
2. L and R subtrees of the root have equal height -> NO!!! This leads to a double chain
3. L and R subtrees have equal number of nodes -> NOE!!!! This leads to a perfect tree

### AVL Balance Conditions:
<span style="color:rgb(255, 192, 0)">The left and right subtrees of every node have heights differing by at most 1</span>

Definition: `balance(x) = height(x.left) - height(x.right)`
AVL property: $-1 \leq \text{ balance}(x) \leq 1$, for every node $x$. 
- Ensures small depth 
- and easy to maintain
Height of a null tree is -1, single node is 0

### What if you insert an item and it's not balanced anymore?
- During the lecture, Ruth draws a green box around the node that has a violation of the BST property
- AVL `find` is the same as BST `find`
- AVL `delete` -> easy way is to use lazy deletion

Now, how do we maintain balance with `insert`:
1. Let b be the node where an imbalance occurs (green box)
2. There are 4 cases to consider. The insertion is in the 
	1. L subtree of the L child of b
	2. R subtree of the L child of b
	3. L subtree of the R child of b
	4. R subtree of the R child of b
3. Idea: Cases 1 and 4 are solved by a single rotation
4. Cases 2 & 3 are solved by a double rotation

---
Back to: [[CSE 332 A - Class Details]]

#ComputerScience