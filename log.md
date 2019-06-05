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

Union Find: 
Trie: 

