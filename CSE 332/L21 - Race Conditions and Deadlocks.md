28 February 2025

---
### Quick notes
- 

### To do
- [x] Finish EX09 ✅ 2025-03-02
- [ ] Finish EX10

---
## Panopto Lecture Notes

Race Conditions: Data Races vs Bad Interleavings.

### What is a race condition?
- A race condition occurs when the computation result depends on scheduling
	- If T1 and T2 happened to get scheduled in a certain way, things go wrong. 
	- So we need to write programs that work independent of scheduling.
- Race conditions are bugs that only exist due to concurrency
- Typically, the problem is that some intermediate state can be seen by another thread [for example a node can be partially inserted into a linkedlist but pointers havent updated so things break.]

| Type of Race Conditions | Data Races                                                                                                                                                    | Bad Interleavings                                                                                                                                                                                                                           |
| ----------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| What is it              | Two different threads potentially write a variable at the same time<br><br>One thread is potentially writing a variable when another is reading the variable. | a situation in concurrent programming where the execution order of multiple threads (or processes) results in an incorrect outcome due to an unfavorable sequence of operations, even if the individual operations are correct on their own |
| Important things        | "Potentially" is important                                                                                                                                    | Creates intermediate states that are exposed                                                                                                                                                                                                |
| Non-example             | Simultaneous reading                                                                                                                                          |                                                                                                                                                                                                                                             |
|                         |                                                                                                                                                               |                                                                                                                                                                                                                                             |

### Exercise 10 Table

| Thread A                           | Thread B                           |
| ---------------------------------- | ---------------------------------- |
| Line 2: `lk.acquire();`            |                                    |
| Line 3: `lk.release();`            |                                    |
| Line 4: `int b = getBalance();`    |                                    |
| Line 5: `lk.acquire();`            |                                    |
| Line 6: `if (amount > b) {`        |                                    |
| Line 7: `    lk.release();`        |                                    |
| Line 8: `    throw new ...`        |                                    |
| Line 9: `}`                        |                                    |
| Line 10: `lk.release();`           |                                    |
|                                    | Line 2: `lk.acquire();`            |
|                                    | Line 3: `lk.release();`            |
|                                    | Line 4: `int b = getBalance();`    |
|                                    | Line 5: `lk.acquire();`            |
|                                    | Line 6: `if (amount > b) {`        |
|                                    | Line 7: `    lk.release();`        |
|                                    | Line 8: `    throw new ...`        |
|                                    | Line 9: `}`                        |
|                                    | Line 10: `lk.release();`           |
|                                    | Line 11: `setBalance(b - amount);` |
|                                    | Line 12: `lk.acquire();`           |
|                                    | Line 13: `lk.release();`           |
| Line 11: `setBalance(b - amount);` | Complete                           |
| Line 12: `lk.acquire();`           |                                    |
| Line 13: `lk.release();`           |                                    |
| Complete                           | Forgotten :(                       |


---
Back to: [[CSE 332 A - Class Details]]

#ComputerScience