# 10953 (A+B - 6)

문제 링크: <https://www.acmicpc.net/problem/10953>

<br>

## Python3

```python
T = int(input())

for _ in range(T):
    raw = input().split(',')
    A, B = int(raw[0]), int(raw[1])
    print(A + B)
```
