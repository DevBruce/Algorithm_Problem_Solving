# 11945 (뜨거운 붕어빵)

문제 링크: <https://www.acmicpc.net/problem/11945>

<br>

## Python3

```python
raw = input().split()
N, M = int(raw[0]), int(raw[1])

for _ in range(N):
    print(input()[::-1])
```
