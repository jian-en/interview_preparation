# Week 5

## Day 1
https://leetcode.com/problems/convert-sorted-list-to-binary-search-tree/
1. Singly linked list: fast/slow pointer
```python3
def findMiddle(self, head):
        fast_ptr = slow_ptr = head
        prev_ptr = None
        
        while fast_ptr and fast_ptr.next:
            
            prev_ptr = slow_ptr
            slow_ptr = slow_ptr.next
            fast_ptr = fast_ptr.next.next
        if prev_ptr:
            prev_ptr.next = None
        return slow_ptr
```
## Day 2
1. Determine if a string is "()" valid or not
## Day 3
1. Tree traversal in three ways
2. Graph: DFS - iterative + recursive + Union Find
## Day 4
https://leetcode.com/problems/recover-binary-search-tree/submissions/
1. Tree traversal + Morris Traversal -> https://www.cnblogs.com/AnnieKim/archive/2013/06/15/morristraversal.html
## Day 5
1. Topographical Sort: BFS
2. DFS -> three status (unvisited, visited, finished)

### Princeton/MIT Review
1. Merge Sort
2. BST
3. Heap
3. Sweep line
4. Trie
5. Topological Sort



Princeton algorithms:
Part I focuses on elementary data structures, sorting, and searching. Topics include union−find, binary search, stacks, queues, bags, insertion sort, selection sort, shellsort, quicksort, 3-way quicksort, mergesort, heapsort, binary heaps, binary search trees, red−black trees, separate-chaining and linear-probing hash tables, Graham scan, and kd-trees.
https://www.coursera.org/learn/algorithms-part1/home/welcome


Part II focuses on graph and string-processing algorithms. Topics include depth-first search, breadth-first search, topological sort, Kosaraju−Sharir, Kruskal, Prim, Dijkistra, Bellman−Ford, Ford−Fulkerson, LSD radix sort, MSD radix sort, 3-way radix quicksort, multiway tries, ternary search tries, Knuth−Morris−Pratt, Boyer−Moore, Rabin–Karp, regular expression matching, run-length coding, Huffman coding, LZW compression and Burrows−Wheeler transform. Part II also introduces reductions and intractability, including the P = NP problem.
https://www.coursera.org/learn/algorithms-part2/home/week/6


