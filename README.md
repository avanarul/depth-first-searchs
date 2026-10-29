# Experiment No. 2: Implement Depth First Search Traversal of a Graph

## AIM
To implement Depth First Search (DFS) traversal of a graph using Python 3.

## THEORY
Depth First Search (DFS) is a graph traversal algorithm used to explore all the vertices of a graph. It starts from a selected node and explores as far as possible along each branch before backtracking.

Unlike trees, graphs may contain cycles, so a visited array or set is used to avoid visiting the same node more than once. DFS can be implemented using a stack or recursion.

## ALGORITHM
1. Construct a graph using nodes and edges.
2. Initialize the visited structure and an empty path.
3. Select the starting node.
4. Mark the starting node as visited and add it to the traversal path.
5. Visit each unvisited neighboring node recursively.
6. Continue until all reachable nodes have been visited.
7. Print the DFS traversal path.

## PROGRAM

```python
from collections import defaultdict

def dfs(graph, start, visited, path):
    path.append(start)
    visited[start] = True

    for neighbour in graph[start]:
        if not visited[neighbour]:
            dfs(graph, neighbour, visited, path)

    return path

graph = defaultdict(list)

n, e = map(int, input().split())

for i in range(e):
    u, v = input().split()
    graph[u].append(v)
    graph[v].append(u)

start = 'A'
visited = defaultdict(bool)
path = []

traversedpath = dfs(graph, start, visited, path)
print(traversedpath)
```

## SAMPLE INPUT 1

```text
8 9
A B
A C
B E
C D
B D
C G
D F
G F
F H
```

## SAMPLE OUTPUT 1

```text
['A', 'B', 'E', 'D', 'C', 'G', 'F', 'H']
```

## OUTPUT

<img width="1592" height="686" alt="image" src="https://github.com/user-attachments/assets/0303def5-615f-4734-a2de-de2631336329" />


**Note:** The second sample uses numeric node labels, so change `start = 'A'` to `start = '0'` before running it.

## RESULT
Thus, a graph was constructed and Depth First Search traversal was implemented successfully using Python 3.
