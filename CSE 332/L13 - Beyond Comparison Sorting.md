5 February 2025

---
### Quick notes
- 

### To do
- [ ] START EX05 NOWWW🔺 

---
## Lecture Notes

### Quick Sort
>$O(n \log n)$ average case, $O(n^2)$ worst-case 
>Does not require auxiliary space
- Pick a "pivot" element [chops the data into 2 pieces]
	- Preferably an element close to the median
- Divide elements into < pivot and > pivot
- Sort the two divisions recursively on each
- The resulting answer is a sorted array that's less than the pivot or a sorted array that's greater than the pivot

[How do you choose a pivot? If you want it to be near the median, how do you find the median? Does that not require the array to be sorted first?]

Best-case: pivot is the median -> T(n) = 2 T(n / 2) + n -> O(n log n)[linear time partition]
Worst-case: pivot is the greatest/least -> T(n) = T(n - 1) + n -> O(n^2)

#### Picking the Pivot
- You can either always pick the first element or the last element of the input array [what if it's already sorted though?]
- What if you take a random element? [but pseudo-random number generator can be slow]
	- Median of 3: `arr[lo]`, `arr[hi-1]`, `arr[(hi + lo) / 2]`

#### Partitioning
- [look at slides]
- Step 1: pick pivot
- Step 2: move pivot to the `lo` position. 
- Step 3: break arrays into two equal pieces by swapping
	- Each pointer moves on their own, not simultaneously
- Step 4: Swap pivot with the element where both pointers end up on

Example of partitioning: [Data Structures and Algorithms: Quick Sort](https://www.eecs.umich.edu/courses/eecs380/ALG/qsort1a.html#:~:text=They%20are%20moved%20towards%20the,until%20they%20%22cross%20over%22.)

Stable - items in input with the same value end up in the same order as when they began.
In place - sorted items occupy the same space as the original items. 

### External Sorting
[READ THE SLIDE THAT SHE SKIPPED OVER]

### Other Sorting Techniques
Comparison lower bound: $\Omega(n \log n)$ -> slow because we HAVE to do comparisons

A ==decision tree== is a tree where its nodes contain a "set of remaining possibilities". At the root, anything is possible and there are no options eliminated. The edges are always "answers from a comparison". 

Related: [Decision Trees in Machine Learning Explained - Seldon](https://www.seldon.io/decision-trees-in-machine-learning#:~:text=Decision%20trees%20are%20an%20approach,categorise%20or%20classify%20an%20object.)

### Specialized Algorithms: Bucket/Radix Sort - O(n)
**Bucket Sort** -- used when we know the range of the integers to be sorted. (1, B)
1. Create an array of size B, and put each element into its proper bucket
2. If the data is only integers, no need to store more than a count of how many times that bucket has been used
3. Linear pass through array of buckets -> array of sorted integers [Takes O(N + B) because you have to pass through the buckets (B) and then write them all out (N)]

**Radix Sort** - when we use larger numbers [Stable]
- The "radix" is the base of a number system. [ASCII strings might use 128]
1. First pass: Bucket sort on one digit at a time
	1. Number of buckets = radix
	2. [complete from slides]
2. First pass: Iterate through and collect into a list
3. Second pass: stable bucket sort by tens digit
4. Third pass: sort by hundreds digit
5. nth pass: sort by nth digit

[Do radix sort practice on the slides]





---
Back to: [class details]

#ComputerScience