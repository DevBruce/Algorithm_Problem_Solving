# 2439 (별 찍기 - 2)

문제 링크: <https://www.acmicpc.net/problem/2439>

<br>

## Python3

```python
N = int(input())

for i in range(1, N+1):
    print(' ' * (N-i), '*' * i, sep='')
```
