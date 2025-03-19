3 March 2025

---
### Quick notes
- lmfao Ruth made us take an oath of never putting data races in our code

### To do
- [ ] Review EX10 answers with study group
- [ ] Read Grossman notes for more information about concurrency

---
## Lecture Notes
Data races are two different threads manipulating information at the same time. If we have mutual exclusion--this data racing can be easily prevented. But we still need to beware of bad interleavings. 

Slide 7: example of a race condition but not a data race. This is not a data race because it calls pop() and push() which are synchronized. For example, if we add a line `print index` right after the beginning of the peek() method, we could be accessing the index while either pop() or push() is being performed. 

"Data race" is like racing to get simultaneous access. 

### Conventional wisdom
Yafqa said there would be some conventional wisdom. 
[See section 8 in Grossman Notes]

For every memory location, you need to obey at least one of the following:
1. Thread-local -- do not use the location in more than 1 thread
	- Whenever its possible, don't share resources
2. Immutable -- do not write to the memory location
	- Whenever possible, do not update objects, make new objects instead!
3. Shared-and-mutable: Use synchronization to control access to the location.
	- Keep it synchronized!!!
	- REMEMBER THERE SHALL BE NO DATA RACES
	- A Java or C program with a data race is almost always wrong...

![[memory_conventional_Wisdom.png]]

### For the rest (following #3)
Guideline #0: NO DATA RACES!
Guideline #1: Use consistent locking--for each location needing synchronization, have a lock that is always held when reading/writing
	Lock Granularity: **Coarse-grained** is fewer locks, more objects per lock [one lock for all bank accounts]; **Fine-grained** is more locks, fewer objects per lock [one lock per bank account]
Guideline #2: Start with coarse-grained (simpler) and move to finegrained (performance) only if contention on the coarser locks becomes an issue.
Guideline #3: Think about atomicity first and locks second
Guideline #4: Use built-in libraries whenever they meet your needs


Example:
> If we had a separate chaining hashtable, is coarse-grained or fine-grained supporting more concurrency for `insert` and `lookup`? 

Fine-grained is better for these operations because if they're different buckets, you can do them at the same time. If it was course-grained, you'd force the two operations to be sequential. 

>Which makes implementing `resize` easier? and how would you do it?

For resize, we're handling the whole hashtable, so acquiring a lock for an entire hashtable is easier than obtaining all the locks for each buckets. 

>If a hashtable has a `numElements` field, maintaining it will destroy the benefits of using separate locks for each bucket, why?

If you had a fine-grained lock, then you need to update `numElements` at the same time, which might cause

### Deadlock

Not the valorant agent. 

Basically when two threads need to acquire the same lock, but they're already taken by the other thread. Therefore, "a whole lot of nothing happens" - Ruth. 
[Dining philosophers problem]

In our lecture example where you transfer to another bank, how do we prevent deadlocks?
- Make a smaller critical section
- Coarsen lock granularity
- Give every bank account a unique number and always acquire it in that order. 




---
Back to: [[CSE 332 A - Class Details]]

#ComputerScience