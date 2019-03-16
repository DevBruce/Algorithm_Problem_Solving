# 11724 (연결 요소의 개수)

문제 링크: <https://www.acmicpc.net/problem/11724>  

<br>

- DFS | BFS

<br>

## 특이사항

`input()` 사용시 시간 초과가 발생하므로  
`sys.stdin.readline()` 을 활용한다.  

<br>

## Python3

```python
import sys
sys_input = sys.stdin.readline


# Define DFS (stack)
def dfs(graph, start_vertex):
    visited = set()
    stack = [start_vertex]
    while stack:
        vertex = stack.pop()
        if vertex not in visited:
            visited.add(vertex)
            stack.extend(graph[vertex])
    return visited


# N: Number of vertexes, M: Number of edges
N, M = map(int, sys_input().split())

# Set Graph
graph = {n:set() for n in range(1, N+1)}
for _ in range(M):
    from_, to = map(int, sys_input().split())
    graph[from_].add(to)
    graph[to].add(from_)

cnt = 0
visited = set()
for v in range(1, N+1):
    if v not in visited:
        visited.update(dfs(graph, v))
        cnt += 1

print(cnt)
```
