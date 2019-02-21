# 11021 (A+B - 7)

문제 링크: <https://www.acmicpc.net/problem/11021>

<br>

## Python3

```python
T = int(input())

for n in range(T):
    A, B = map(int, input().split())
    print(f'Case #{n+1}: {A + B}')
```
