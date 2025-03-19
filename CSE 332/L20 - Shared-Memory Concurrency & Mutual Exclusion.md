26 February 2025

---
### Quick notes
- Guest lecturer Yafqa!

### To do
- [ ] Start EX08

---
## Lecture Notes
- If two threads had access to a shared data structure, some of the operations might be lost because of pointers re-referencing to a new item

**Concurrency**: Correctly and efficiently managing access to shared resources from multiple possibly-simultaneous clients
	-> requires coordination [synchronization to avoid incorrect simultaneous access]
	-> we want to block a thread until the resource is free, aka blocking another thread until it is "done using what we need", not "completely done executing"

"Interleaving" is when a second call starting before the first finishing. If the calls refer to different resources, there is no issue. 

**Example:** If you're withdrawing from a bank with two different calls `x.withdraw(100)` and `y.withdraw(75)` from a starting balance of `150`, a withdraw too large exception arises only when processes run sequentially. The possible ending balances of this code includes `50` or `75`.

### Mutual Exclusion
Fixing the issue: Allow at most one thread to withdraw from account A at a time. [another thread must wait]
- The area of the code that we want to have mutual exclusion is called the "critical section"

### Mutual Exclusion Lock ADT
- `new`: make a new lock, initially "not held"
- `acquire`: blocks if this lock is already currently "held" [checking and setting happens at the same time]
- `release`: makes the lock 'not held'

#### Re-entrant Lock 
- In a single thread, once a lock is acquired, then you can continue acquiring that lock
- On `acquire` -> it does not block, but increments the count
- On `release` -> if count is greater than 0, count is decremented, if it is equal to 0, then it releases

`java.util.concurrent.locks.ReentrantLock` has methods `lock()` and `unlock()`

REMEMBER TO UNLOCK BEFORE EXITING THE THREAD!!!
- this is why some people usually put their code in a `try {}` block.
- but Java also has `synchronized`, which is an alternative to declaring a `ReentrantLock`

```java
synchronized(expression) {
	// statements
}

synchronized void method() {
	// etc
}
```







---
Back to: [[CSE 332 A - Class Details]]

#ComputerScience