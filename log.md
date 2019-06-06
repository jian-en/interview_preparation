# Week 1 - 2
Dynamic Programming:

Graph - adjacent:
Undirected graph
```python3
from collections import defaultdict
graph = defaultdict(list)
if connected(i, j):
    # Symmetric
    graph[i].append(j)
    graph[j].append(i)
```

DFS:
Iterative Solution - stack
```python3
seen = [False] * num_of_elements
for i in range(num_of_elements):
    if not seen[i]:
        stack = [i]
        seen[i] = True
        while stack:
            item = stack.pop()
            process(item)
            for neighbor in neighbors:
                if not seen[neighbor]:
                    seen[neighbor] = True
                    stack.append(neighbor)
```

Recursive Solution:
```python3
graph = defaultdict(set)
def dfs(source, target):
    if source not in seen:
        seen.add(source)
        if source == target: return True
        return any(dfs(nei, target) for nei in neighbors)
for u, v in edges:
    seen = set()
    if u in graph and v in graph and dfs(u, v):
        return u, v
    graph[u].add(v)
    graph[v].add(u)
```

Union Find: 

Quick Find:
```python3
class UF:

    def __init__(self, N):
        self.nodes = list(range(N))
    
    def root(self, i):  # find
        return self.nodes[i]
        
    def connected(self, i, j):
        return self.nodes[i] == self.nodes[j]
        
    def union(self, i, j): # union too expensive, trees are flat but expensive to keep
        iid = self.nodes[i]
        jid = self.nodes[j]
        for index in range(N):
            if self.nodes[index] == jid:
                self.nodes[index] = iid
```

Quick Union:
```python3
class UF:
    def __init__(self, N):
        self.nodes = list(range(N))
        
    def root(self, i): # find: expensive
        while self.nodes[i] != i:
            i = self.nodes[i]
        return i
        
    def connected(self, i, j):
        return root(i) == root(j)
        
    def union(self, i, j): # trees get tall
        iid = self.root(i)
        jid = self.root(j)
        self.nodes[iid] = jid
```

Weighted quick union:

```python3
class UF:
    def __init__(self, N):
        self.nodes = list(range(N))
        self.size = [1] * N
    
    def root(self, i):
        while self.nodes[i] != i:
            i = self.nodes[i]
        return i
        
    def connected(self, i, j):
        return self.root(i) == self.root(j)
        
    def union(self, i, j): # depth of any node is at most lgN
        iid = self.root(i)
        jid = self.root(j)
        if self.size[iid] > self.size[jid]:
            self.nodes[jid] = iid
            self.size[iid] += self.size[jid]
        else:
            self.nodes[iid] = jid
            self.size[jid] += self.size[iid]
```

Trie: 

Princeton algorithms:
Part I focuses on elementary data structures, sorting, and searching. Topics include union−find, binary search, stacks, queues, bags, insertion sort, selection sort, shellsort, quicksort, 3-way quicksort, mergesort, heapsort, binary heaps, binary search trees, red−black trees, separate-chaining and linear-probing hash tables, Graham scan, and kd-trees.
https://www.coursera.org/learn/algorithms-part1/home/welcome


Part II focuses on graph and string-processing algorithms. Topics include depth-first search, breadth-first search, topological sort, Kosaraju−Sharir, Kruskal, Prim, Dijkistra, Bellman−Ford, Ford−Fulkerson, LSD radix sort, MSD radix sort, 3-way radix quicksort, multiway tries, ternary search tries, Knuth−Morris−Pratt, Boyer−Moore, Rabin–Karp, regular expression matching, run-length coding, Huffman coding, LZW compression and Burrows−Wheeler transform. Part II also introduces reductions and intractability, including the P = NP problem.
https://www.coursera.org/learn/algorithms-part2/home/week/6


