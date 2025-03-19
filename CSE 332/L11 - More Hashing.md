31 January 2025

---
### Quick notes
- EX05 is getting posted later tonight: programming exercise. 
- $\lambda$ indicates how full a hash table is

### To do
- [x] Finish EX04 ✅ 2025-02-02
- [ ] Start EX05
- [ ] Review sample exams for midterm on course website
- [x] Survey from Ruth on canvas ✅ 2025-02-02

---
## Lecture Notes

An extension from Wednesday's lecture: [[L10 - Hashing]]. Last time, we talked about separate chaining. Now, we go through the other methods: 
- Open addressing
	- Linear probing
	- Quadratic probing
	- Double hashing

### Linear Probing Algorithm
> aka going until you find another empty space

If h(key) is already full, 
-> try (h(key) + 1) % TableSize. If full...
-> try (h(key) + 2) % TableSize. If full... 
-> try (h(key) + 3) % TableSize. If full... continue on

`insert` finds an open table position using a probe function

How should `find` work? If the value is in the table? If it's not there?
- Compute the hash function -> check if the key is at the index -> if not, probe until you find it
- It's an unsuccessful search when you reach an empty position

Worst case scenario for `find`?
- If the entire hash table was full and the element you want to find isn't there. 
- Or, if the element isn't in the hash table to begin with.

How should we implement `delete`?
- **Must use** Lazy deletion
- It marks that there is no data (instead of empty), so that the algorithm can keep on probing to search for other elements.

#### Difference Between Linear Probing and Separate Chaining

How does **open addressing with linear probing** compare to **separate chaining**.
- Open addressing with linear probing saves memory (no linked list for each bucket)
- In open addressing, can't insert if the array is full [have to rehash by resizing array which is roughly twice as big but the size of a prime number]
	- In separate chaining, another linked list node is added
	- Rehashing is expensive, since originally the values are calculated using the hashTable size. Then you have to recalculate the hash function for every element in the table. 
- Worst case is the same for either option. 

#### Why is Linear Probing Bad?
- It tends to produce clusters, which leads to long probe sequences [aka] <span style="color:rgb(255, 192, 0)">primary clustering</span>. It forms big "blobs" -> causes a costly runtime for `find`

[peep the slide with "trivial" that she skipped]


soooo.... we have a new approach
### Quadratic Probing
- This is effectively the same as linear probing, but it jumps a quadratic proportion to avoid primary clustering. 

If h(key) is already full, 
-> try (h(key) + 1) % TableSize. If full...
-> try (h(key) + 4) % TableSize. If full... 
-> try (h(key) + 9) % TableSize. If full... continue on

...but it causes <span style="color:rgb(255, 192, 0)">secondary clustering</span>

### Double Hashing
Given two good hash functions h and g, and two different keys, it's very unlikely that these two functions would lead to the values having a collision.

`f(i) = i * g(key)`

Probe sequence
[edit this]
-> try (h(key) + 1) % TableSize. If full...
-> try (h(key) + 4) % TableSize. If full... 
-> try (h(key) + 9) % TableSize. If full... continue on


---
Back to: [[CSE 332 A - Class Details]]

#ComputerScience