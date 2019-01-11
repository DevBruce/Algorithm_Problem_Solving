# 11022 (A+B - 8)

문제 링크: <https://www.acmicpc.net/problem/11022>

<br>

## Python3

```python
T = int(input())

for n in range(T):
    raw = input().split()
    A, B = int(raw[0]), int(raw[1])
    print(f'Case #{n+1}: {A} + {B} = {A + B}')
```
