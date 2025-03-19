27 January 2025

---
### Quick notes
- AVL data structures have a field within the node that keeps the subtree's height
- These trees are cool

### To do
- [x] Rewrite EX03 and resubmit ✅ 2025-01-27
- [x] Call trailside ✅ 2025-01-27
- [ ] Pre-lecture for 391 due TOMORROW 🔺 
- [x] Call trailside to confirm new application deatils ✅ 2025-01-27
- [ ] Start EX04 (hopefully)
- [ ] Look at end of lecture slides -- more AVL rotation examples + golden ratio


---
## Lecture Notes

### Double Rotations
Last lecture, we talked about Single Rotations in [[L8 - AVL Trees]]. 

Single rotations can be used to solve AVL balance issues for leaf nodes on the edge, but what if the unbalanced leaf node was in the middle?

[AVL tree - Wikipedia](https://en.wikipedia.org/wiki/AVL_tree)

**Singular Rotation Recap**
- The rotation only happens at the first instance of the imbalance
- Rotation is constant amount of work -- retrieving the heights of both subtrees and then adding one to one of them

Double rotation is rotation both ways. 

If we have a tree that shaped, with 1 being the problem node:
1 -> 6 <- 3, we first do a rotation with the child of 1 and the grandchild, and we have
1 -> 3 -> 6, then we do a left rotation to put 3 at the top:
1 <- 3 -> 6

Pseudocode algorithm:
1. Rotate problematic child and grandchild
2. Rotate between self and new child


[look at golden ratio slide]



---
Back to: [[CSE 332 A - Class Details]]

#ComputerScience