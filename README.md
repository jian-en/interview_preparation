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


# Sorting
## QuickSort

# Dynamic Programming
* Break it into two problems: forward traverse and backward traverse
