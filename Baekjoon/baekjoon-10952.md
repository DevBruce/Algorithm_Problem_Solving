# 10952 (A+B - 5)

문제 링크: <https://www.acmicpc.net/problem/10952>

<br>

## Python3

```python
while True:
    raw = input().split()
    A, B = int(raw[0]), int(raw[1])
    if A == 0 and B == 0:
        break
    print(A + B)
```
