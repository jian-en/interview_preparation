# Python3 Idioms
## Swap
* a, b = b, a
## Math
* 5 / 2 == 2.5, 5//2 == 2
* +/- math.inf
* math.log10, math.log(base e), math.log2
## Matrix
* Transpose a matrix
```python3
M = [[1,2,3],[4,5,6],[7,8,9]]
print(list(zip(*M))) # [(1, 4, 7), (2, 5, 8), (3, 6, 9)]
```
* Matrix traverse
```python3
directions = [(0, 1), (1, 0), (0, -1), (-1, 0)] # right - down - left - up
```
## Char
* 26 letters, chr <=> ord
* '1'.isdigit()

## Other
* functools.reduce(lambda a,b : a if a > b else b,list)
* "".join(list(reversed("fujian")))
* list.reverse()  # in-place reverse
* \[\[0 for x in range(columns)] for y in range(rows)]
* zip(\*iterable) can zip multiple iterables
* encode info in the existing data structure: board[y][x] ^= 256 for letters

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

### Trie
![trie](trie.png)

```python3
class Node:

    def __init__(self):
        self.letters = dict()
        self.is_word = False

class Trie:

    def __init__(self):
        self.root = Node()

    def insert_word(self, word):
        node = self.root
        for c in word:
            if c not in node.letters:
                node.letters[c] = Node()
            node = node.letters[c]
        node.is_word = True

    def search_word(self, word):
        node = self.root
        for c in word:
            if c not in node.letters:
                return False
            node = node.letters[c]
        return node.is_word

    def _delete(self, node, word, index):
        if node.is_word and node.letters:
            node.is_word = False
            return node
        elif node.is_word and not node.letters:
            return None
        else:
            val = self._delete(node.letters[word[index]], word, index + 1)
            if val is None:
                del node.letters[word[index]]
                if not node.letters:
                    return None
            return node

    def delete_word(self, word):
        if self.search_word(word):
            self._delete(self.root, word, 0)
```

### Deque

### Stack

* Two stacks technique (the other stack records more information, eg: minStack, maxStack)

# Bit Manipulation
* num &(num-1) == 0  <=> num is power of 2
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
start, end = 0, 0 + Hashmap | find substring that satisfies some restrictions

# Sorting
## QuickSort

## Toposort

# Breadth First Search

# Backtracking

* Recursion on every possible solutions
* Use memo to prune the branches

# Dynamic Programming
* Define the transition formula
* Break it into two problems: forward traverse and backward traverse
* Top-bottom approach + memorization -> Recursive
* Bottom-top approach + result set -> Iterative

# Complexity
* Draw the recursion tree

