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
        self.nodes = [None] + list(range(1, N+1))
        
    def connected(self, i, j):
        return self.nodes[i] == self.nodes[j]
        
    def union(self, i, j):
        iid = self.nodes[i]
        jid = self.nodes[j]
        for index in range(1, len(self.nodes) + 1):
            if self.nodes[index] == jid:
                self.nodes[index] = iid
```
Trie: 

