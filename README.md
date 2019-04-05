# Python3 Idioms
## Math
* 5 / 2 == 2.5, 5//2 == 2
* +/- math.inf
* math.log10
## Other
* functools.reduce(lambda a,b : a if a > b else b,list)
* "".join(list(reversed("fujian")))
* [[0 for x in range(columns)] for y in range(rows)]
## Data structure
### Namedtuple:
* Person = collections.namedtuple('Person', 'name age gender')

# Bit Manipulation
* num &(num-1) == 0  ⇔ num is power of 2

# Search
* Linear search | randomly VS sorted
* Binary Search
```python3
# Search
import bisect
bisect.bisect([1,2,3,4], 3) # return 3
bisect.bisect_left([1,2,3,4], 3) # return 2
```


# Sorting
## QuickSort

# Dynamic Programming
* Break it into two problems: forward traverse and backward traverse
