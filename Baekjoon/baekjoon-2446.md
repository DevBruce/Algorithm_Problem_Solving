# 2446 (별 찍기 - 9)

문제 링크: <https://www.acmicpc.net/problem/2446>

<br>

## Python3

```python
N = int(input())

for i in range(N, 1-1, -1):
    print(' ' * (N-i), '*' * (2*i-1), sep='')
for i in range(1, N):
    print(' ' * (N-1-i), '*' * (2*i+1), sep='')
```
