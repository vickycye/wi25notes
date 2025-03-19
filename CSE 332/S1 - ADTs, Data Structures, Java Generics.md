9 January 2025

---
### Quick Notes
- Medha is cool
- When writing generics, we want the most "simple" way to write the types, so sometimes if we want, for example, a ListPair to be implemented of type E, we will have just \<E\> in the class header.

### To do
- 

---
### Section Notes

### Abstract Data Types (ADT)

ADT -> Data Structures -> Implementation

| ADT   | Operations             | DataStructures                              |
| ----- | ---------------------- | ------------------------------------------- |
| List  | add, remove, get       | arraylist, linkedlist                       |
| Stack | push, pop, peek        | arraylist, linkedlist                       |
| Queue | enqueue, dequeue, peek | arraylist, linkedlist                       |
| Set   | add, remove, contains  | arraylist, linkedlist, binary tree, hashset |

### Java Generics \<T\>

This is an extension of the content learned in [[L17 - Generics]] from [[CS 211 - Class Details]]
`ArrayList<String> myArrayList = new ArrayList<>();`

| ADT   | Operations                                                         | Data Structures                             |
| ----- | ------------------------------------------------------------------ | ------------------------------------------- |
| Pair  | set first, get first, set second, get second (getters and setters) | an object with a first and second parameter |
| Tuple | Get ith, set ith                                                   | an object with an array                     |
- You can also have <`item 1, item 2`> in generics when two data types are different.

Object casting is necessary since Java doesn't allow `new T[5]`
```
data = (T[]) new Object[tuple.length]
```

- Can also use inheritance, such as `public class LikeAnimalPair<T extends Animal>`, where `Animal` can be either Cats, Dogs, or whatever else is in an `Animal` class.

For comparable interface, this is an example of what "a pair of items such that both of them implement the comparable interface. A comparable pair must itself be comparable!"
`public class ComparablePair<T extends Comparable<T>, E extends Comparable<E> implements Comparable<ComparablePair<T, E>>` 


---
Corresponding Lecture: [[L2 - Algorithm Analysis Part 1]]

Back to: [[CSE 332 A - Class Details]]

#ComputerScience 
