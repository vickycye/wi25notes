29 January 2025

---
### Quick notes
- Tomorrow section is AVL trees
- Apparently hashing is not in the textbook
- Using prime numbers for hashtable size is often common
- Ruth's favorite phrase to say is "My enemy"

### To do
- [ ] Start EX04 -- due Friday
- [ ] STAT 311 - Practice problems week 2
- [ ] STAT 311 - Practice problems week 3

---
## Lecture Notes

### Intro to Hashing

Implemented with dictionary
We have a "really big array"

- `insert()` -> O(1) -- just assign value to key 
- `find()` -> O(1)
- `delete()` -> O(1) -- no shifting elements, just delete the value

One downside though,,,, $n$ is huge, a lotta waste of space.

- Hash tables have a "hash function", it can either be a mathematical equation or a full blown function

Ideal hash functions are fast to compute and they should hash keys to unique indices

When two "used" keys are hashed to the same index, its called a "collision", 
which are often impossible in theory, but common in practice to occur -> handle collision

To store keys of type `E`, we need to be able to:
1. Test equality, is this the `E` im looking for?
2. Hashable: convert any `E` to an int

![[hashing_graphic.png]]

### Why? When

If you have objects with several fields, it's good to have the most "identifiable fields" to contribute to the hash function to avoid collisions

For example, if you have a class `Person` with fields first, middle, last names and birthdate, we need to choose something that will best represent a unique person.
-> The best scenario would use all the fields, but....

<span style="color:rgb(255, 192, 0)">There is an inherent trade-off: hashing-time vs. collision-advoidance</span>

Examples
1. $h(k) = s_0$
2. $h(k) = \sum_{i = 0}^{m - 1} s_i$
3. $h(k) = \sum_{i = 0}^{m - 1} s_i \cdot 37^i$

For the first one, collision occurs whenever the first character is the same. 
For the second one, it's summing up all the characters, but if you have strings such as "dsjfdhs" and "sdfjsh", it would collide.
For the third one, we're multiplying by a prime number to enlarge the array and avoid collision, ruth said "positional number system"

> The most common Java hash multiplier is 31, and here is why:

[Why does Java's hashCode() in String use 31 as a multiplier? - Stack Overflow](https://stackoverflow.com/questions/299304/why-does-javas-hashcode-in-string-use-31-as-a-multiplier)

**Example**
How would you hash differently if all your strings were web addresses, (URLs)?

Depends on what type of website you're hashing, if it's for a specific platform, such as Stack Overflow, you can hash by discussion ID, obtained by regex matching.

### Collisions

<span style="color:rgb(112, 48, 160)">Definition: When two keys map to the same location in the hash table</span>

Collision resolutions:
- Separate Chaining
- Open addressing
	- Linear probing
	- Quadratic probing
	- Double hashing

#### Separate Chaining
Chaining: All keys that map to the same table location are kept in a list [Could be a linked list]

![[separate_chaining_hashing.png]]

Worst case time for find = $O(n)$, [what if all of them were in one chain for one key]

**More Rigorous Separate Chaining Analysis**
Definition: There is a <span style="color:rgb(146, 208, 80)">load factor</span>, $\lambda$, which is $$\lambda = \frac{N}{\text{Table size}}$$
Under chaining, the average number of elements per bucket is [1/5 of the table size?]
If some inserts were followed by random finds, then on average:
- Each successful find compares against $\lambda / 2$ items. 
- Each unsuccessful find compares against $\lambda$ items. 

How big should table size be? Well...... there's an issue of trade off again... 

Book recommends table size = $N$. 





---
Back to: [[CSE 332 A - Class Details]]

#ComputerScience