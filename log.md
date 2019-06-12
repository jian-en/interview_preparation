# Week 3

a = a[:]

# Monotone Stack

## Increasing stack
From the start, find the first smaller from the current pos
```python3
# https://leetcode.com/problems/largest-rectangle-in-histogram/discuss/28917/AC-Python-clean-solution-using-stack-76ms
# left boundary, right boundary
# tricks, append 0 at last, prepend -1 at first
heights.append(0)
        i_stack = [-1]
        i = 0
        max_area = 0
        while i < len(heights):
            if i_stack[-1] == -1 or heights[i] >= heights[i_stack[-1]]:
                i_stack.append(i)
                i += 1
            else:
                while i_stack[-1] != -1 and heights[i] < heights[i_stack[-1]]:
                    current_h_i = i_stack.pop()
                    max_area = max(max_area, heights[current_h_i] * (i - i_stack[-1] - 1))

        return max_area
```

## Decreasing stack

https://blog.csdn.net/liujian20150808/article/details/50752861
https://blog.csdn.net/bxw1992/article/details/77856304
https://www.cnblogs.com/grandyang/p/8887985.html

## Divide and conquer (MergeSort)

## Segment Tree
https://leetcode.com/problems/minimum-area-rectangle/

## Tree Map

## Set Operation
```python3
class Solution(object):
    def areSentencesSimilar(self, words1, words2, pairs):
        if len(words1) != len(words2): return False

        pairset = set(map(tuple, pairs))
        return all(w1 == w2 or (w1, w2) in pairset or (w2, w1) in pairset
                   for w1, w2 in zip(words1, words2))
```

Princeton algorithms:
Part I focuses on elementary data structures, sorting, and searching. Topics include union−find, binary search, stacks, queues, bags, insertion sort, selection sort, shellsort, quicksort, 3-way quicksort, mergesort, heapsort, binary heaps, binary search trees, red−black trees, separate-chaining and linear-probing hash tables, Graham scan, and kd-trees.
https://www.coursera.org/learn/algorithms-part1/home/welcome


Part II focuses on graph and string-processing algorithms. Topics include depth-first search, breadth-first search, topological sort, Kosaraju−Sharir, Kruskal, Prim, Dijkistra, Bellman−Ford, Ford−Fulkerson, LSD radix sort, MSD radix sort, 3-way radix quicksort, multiway tries, ternary search tries, Knuth−Morris−Pratt, Boyer−Moore, Rabin–Karp, regular expression matching, run-length coding, Huffman coding, LZW compression and Burrows−Wheeler transform. Part II also introduces reductions and intractability, including the P = NP problem.
https://www.coursera.org/learn/algorithms-part2/home/week/6


