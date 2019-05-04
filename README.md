# Python3 Idioms
## Math
* 5 / 2 == 2.5, 5//2 == 2
* +/- math.inf
* math.log10
## Matrix
* Transpose a matrix
```python3
M = [[1,2,3],[4,5,6],[7,8,9]]
print(zip(*M))
```
## Char
* 26 letters, chr <=> ord

## Other
* functools.reduce(lambda a,b : a if a > b else b,list)
* "".join(list(reversed("fujian")))
* [[0 for x in range(columns)] for y in range(rows)]
* zip(\*iterable) can zip multiple iterables

## Data structure
### Namedtuple:
* Person = collections.namedtuple('Person', 'name age gender')
### Priority Queue:
```python3
from queue import PriorityQueue

q = PriorityQueue()

q.put((2, 'code'))
q.put((1, 'eat'))
q.put((3, 'sleep'))

while not q.empty():
    next_item = q.get()
    print(next_item)

# Result:
#   (1, 'eat')
#   (2, 'code')
#   (3, 'sleep')
```

### Deque

# Bit Manipulation
* num &(num-1) == 0  ⇔ num is power of 2
* num ^= 1 <=> flip between 0 and 1
* 0, 1 -> 2, 3 | 00, 01 -> 10, 11 => use bits to encode more information

# Search
* Linear search | randomly VS sorted
* Binary Search
```python3
# Search
import bisect
bisect.bisect([1,2,3,3,4], 3) # bisect_right, return 4
bisect.bisect_left([1,2,3,3,4], 3) # return 2
```
```python3
def binary_search(nums, target):
    lo = 0
    hi = len(nums) - 1
    while lo + 1 < hi: # Stop when lo + 1 == hi
        mid = lo + (hi - lo) // 2  # Avoid overflow
        if nums[mid] > target:
            hi = mid  # Invariant: nums[hi] > target => the rightest
        else:
            lo = mid   
            
    if nums[lo] == target:
        return lo
    if nums[hi] == target:
        return hi
    return -1
```
# Two Pointer
## Same direction
start, end = 0, 0 | find substring that satisfies some restrictions

# Sorting
## QuickSort

## Toposort

# Breadth First Search

# Backtracking

# Dynamic Programming
* Define the transition formula
* Break it into two problems: forward traverse and backward traverse
* Top-bottom approach + memorization -> Recursive
* Bottom-top approach + result set -> Iterative

