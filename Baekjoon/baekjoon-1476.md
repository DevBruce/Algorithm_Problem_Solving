# 1476 

문제 링크: <https://www.acmicpc.net/problem/1476>

<br>

## 접근방법

- 브루트 포스

<br>

## Python3

```python
E, S, M = map(int, input().split())

result = 0
e, s, m = 0, 0, 0
while not (e == E and s == S and m == M):
    e = e + 1 if e < 15 else 1
    s = s + 1 if s < 28 else 1
    m = m + 1 if m < 19 else 1
    result += 1
    
print(result)
```
