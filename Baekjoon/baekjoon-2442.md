# 2442 (별 찍기 - 5)

문제 링크: <https://www.acmicpc.net/problem/2442>

<br>

## Python3

```python
N = int(input())

for i in range(1, N+1):
    print(' ' * (N-i), '*' * (2*i - 1), sep='')
```
