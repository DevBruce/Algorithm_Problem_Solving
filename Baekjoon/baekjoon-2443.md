# 2443 (별 찍기 - 6)

문제 링크: <https://www.acmicpc.net/problem/2443>

<br>

## Python3

```python
N = int(input())

for i in range(N, 1-1, -1):
    print(' ' * (N-i), '*' * (2*i - 1), sep='')
```
