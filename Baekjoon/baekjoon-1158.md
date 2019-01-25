# 1158 (조세퍼스 문제)

문제 링크: <https://www.acmicpc.net/problem/1158>

<br>

## 접근방법

- 큐 (Queue)

<br>

## 특이사항

시간 초과 에러를 해결하기 위해서  
`collections` 모듈의 `deque` 를 활용하였다.  

`q.rotate(-1)` 은  
`q.append(q.popleft())` 와 동일하다.

<br>

## Python3

```python
import collections


N, M = map(int, input().split())
result = list()
q = collections.deque(range(1, N+1))

tmp = 0
while q:
    tmp += 1
    if tmp % M == 0:
        result.append(q.popleft())
    else:
        q.rotate(-1)
        
print('<' + str(result)[1:-1] + '>')
```
