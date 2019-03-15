# 1260 (DFS와 BFS)

문제 링크: <https://www.acmicpc.net/problem/1260>

<br>

## 특이사항

문제의 조건  
`정점이 여러 개인 경우에는 정점 번호가 작은 것을 먼저 방문`  
을 유의한다.

<br>

## Python3

```python
# Define DFS (Recursive)
def dfs_visit(graph, vertex, visited):
    visited.append(vertex)
    for v in graph[vertex]:
        if v not in visited:
            dfs_visit(graph, v, visited)

def dfs(graph, start_vertex):
    visited = list()
    dfs_visit(graph, start_vertex, visited)
    return visited


# Define BFS (queue)
def bfs(graph, start_vertex):
    visited = list()
    queue = [start_vertex]
    while queue:
        vertex = queue.pop(0)
        if vertex not in visited:
            visited.append(vertex)
            queue.extend(graph[vertex])
    return visited


# N: Number of Vertexes, M: Number Of Edges, V: 탐색 시작 Vertex
N, M, V = map(int, input().split())
# Make Graph (Edge List)
graph = {n+1:list() for n in range(N)}
# Add edges to graph (bidirectional)
for _ in range(M):
    from_, to = map(int, input().split())
    graph[from_].append(to)
    graph[to].append(from_)
    
# Sort graph (Edge List) for this problem condition
for vertex in graph:
    graph[vertex].sort()
    
# Print Result
print(*dfs(graph, V))
print(*bfs(graph, V))
```
