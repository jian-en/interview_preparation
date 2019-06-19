# Week 4
## Day 1
1. Two Pointer:
```python3
i, j = 0, 0
        
while i < len(s1) and j < len(s2):
  # move i, j accordingly
  # if there is while statement, check the boundary
```

## Day 2:
1. Save data on Trie, count -> Trie in Princeton
2. Greedy Algorithm: https://brilliant.org/wiki/greedy-algorithm/
3. 
```python3
def longest_common_prefix(a, b):
  i = 0
  while i < len(a) and i < len(b) and a[i] == b[i]:
    i += 1
    return i
```
4. isalpha(), split(seq, max_split)
5. collections.Counter / Boundary Count


## Tree Map(BST) - Review BST
## Divide and conquer (Review: MergeSort)
## Segment Tree
## Greedy algorithm
https://leetcode.com/problems/split-array-largest-sum/
https://medium.com/cracking-the-data-science-interview/greedy-algorithm-and-dynamic-programming-a8c019928405
1. Local optimization -> global optimization
## Dynamic algorithm
https://www.programering.com/a/MDOzUzMwATM.html



Princeton algorithms:
Part I focuses on elementary data structures, sorting, and searching. Topics include union−find, binary search, stacks, queues, bags, insertion sort, selection sort, shellsort, quicksort, 3-way quicksort, mergesort, heapsort, binary heaps, binary search trees, red−black trees, separate-chaining and linear-probing hash tables, Graham scan, and kd-trees.
https://www.coursera.org/learn/algorithms-part1/home/welcome


Part II focuses on graph and string-processing algorithms. Topics include depth-first search, breadth-first search, topological sort, Kosaraju−Sharir, Kruskal, Prim, Dijkistra, Bellman−Ford, Ford−Fulkerson, LSD radix sort, MSD radix sort, 3-way radix quicksort, multiway tries, ternary search tries, Knuth−Morris−Pratt, Boyer−Moore, Rabin–Karp, regular expression matching, run-length coding, Huffman coding, LZW compression and Burrows−Wheeler transform. Part II also introduces reductions and intractability, including the P = NP problem.
https://www.coursera.org/learn/algorithms-part2/home/week/6


