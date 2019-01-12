# 10430 (나머지)

문제 링크: <https://www.acmicpc.net/problem/10430>

<br>

## Python3

```python
raw = input().split()
A, B, C = int(raw[0]), int(raw[1]), int(raw[2])

print((A+B)%C)
print((A%C + B%C)%C)
print((A*B)%C)
print(((A%C) * (B%C))%C)
```
