# 2441 (별 찍기 - 4)

문제 링크: <https://www.acmicpc.net/problem/2441>

<br>

## Python3

```python
N = int(input())

for i in range(N):
    print(' ' * i, '*' * (N-i), sep='')
```
