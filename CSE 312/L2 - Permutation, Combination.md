8 January 2025

---
### Quick notes
- Homework comes out tonight
- Programming questions submission on gradescope (can program on Ed)
- Defining `type` in a function parameter or function output doesn't reinforce the variable assignment, it can still be changed from int to string, for example.

### To do
- ~~Homework 1 - set up github repo for this class~~
- ~~Concept check 2~~

---
## Lecture Notes

**Overcounting Strategy**
- For any counting problem, we can start with pretending that the order does matter, then divide the number of orderings of the parts where the order doesn't matter.

>For example, to find the number of anagrams for SEATTLE
>We can overcount to say the total options is $7!$, but two of the letters are the same, $E, T$. There are two of each, so we have $2!$ ways to order them (factorial because that's how you count the number of ways it can be reordered).
>We divide by the number of ways to order the repeated letters, and we get
$$\frac{7!}{2! \cdot 2!}$$
> for the total number of options.

---
### Python Programming Notes

- The type of a variable is not fixed in Python like it is in Java.
- `True` and `False` are capitalized
- A Tuple is denoted with `()`, which is an **immutable, ordered** collection of one or more data items, not necessarily of the same type
- A List is initialized with `[]`, which is a **mutable, ordered** collection of one or more data items, not necessarily of the same type
- A Set is denoted with `set([])`, which is a **mutable, unordered** collection of data type that has no duplicate elements
- A Dictionary is denoted with `{}`, which is a **mutable,** **unordered** collection of data in a `key:value` pair form where each key is unique.

Integer Division: `5 \\ 2 # 2`
Float Division: `5 \ 2    # 2.5`
Exponentiation: `2 ** 3  # 8`

- Must use `+=` operator instead of `++`
- Must cast an integer to a str during concatenation to avoid errors

![[string_formatting.png]]

Range function: `for i in range(start, end, step)`
For lists, can use `list[-1]` to find the last value in the list.
List slicing: `list[start_index (inclusive) : end_index (exclusive)]`

### How to write one-liners (list comprehension)

![[list_of_squares_oneliner.png]]

Lists:
- `append`
- `insert`
- `remove`
- `del list[i]` - delete by position

libraries:
`math`: `import math` or `from math import sqrt`

There can also be default parameter values: `def greet(name:str, greeting:str = "Hello")` -- <mark style="background: #FFF3A3A6;">all the default arguments must come at the end of the function</mark>!

### Main Method in Python
```
# Main Method

def main():
    print("Hello")

# calls main method when this file is run with `python file_name.py` from the terminal
if __name__ == "__main__":
    main()
```

Set operations:
- `in`
- `not in`
- `remove()`
- `len()`
- `add()`
- 
Constructing sets: `x:set = set()` or `x:set = {1, 2, 3}`

Dictionary operations: 
- `dict.keys()`-- returns keyset
Iterating through dictionary:
```
# Iterate through every key first_n in dictionary x
for first_n in x:
  print(first_n + " " + x[first_n])
```

### Example Python Class
```
class Line:
  '''
  This class represents straight lines in slope-intercept form
  ax + b
  '''

  def __init__(self, a, b):
    # Constructor
    self.a = a
    self.b = b
  def get_slope(self):
    return self.a
  def set_intercept(self, b):
    self.b = b
```

`def __init__(self, a, b)` is like a constructor in Java


### numpy introduction

```
# array

import numpy as np

# Convert from list of lists to numpy array! Basically a cast.
c = np.array([[1, 2, 3, 4], [5, 6, 7, 8]])
print(c)

# Creates a 3x4 matrix of 0's
a = np.zeros((3, 4))

# Creates a 2x5x3 matrix (tensor) of 1's
b = np.ones((2, 5, 3))

# Works exactly like range() but returns a np array instead of a range object
# 3 parameters (start, end=length of list, step=1), where end/step are optional
# and have defaults
d = np.arange(1, 10, 3)


```

- `reshape()` changes the dimensions of the array

```
print(np.sum(arr, axis=0)) # Provides the sum based on columns
print(np.sum(arr, axis=1)) # Provides the sum based on rows
```

### Matplotlib
```
import matplotlib.pyplot as plt
import numpy as np

x = np.arange(10)
y = x ** 2
z = 5*x + 7
plt.plot(x, y, color="b", label="y = x^2", linestyle="-")
plt.plot(x, z, color="r", label="z = 5x + 7", linestyle="-.")
plt.legend(loc="upper left")
plt.xlabel("x")
plt.ylabel("f(x)")
plt.title("An interesting graph")
plt.savefig("plot.png")
```



---
Back to: [[CSE 312 A - Class Details]]

#ComputerScience #Stats 