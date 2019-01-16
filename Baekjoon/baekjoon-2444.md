# 2444 (별 찍기 - 7)

문제 링크: <https://www.acmicpc.net/problem/2444>

<br>

## Python3

```python
N = int(input())

for i in range(1, N+1):
    print(' ' * (N-i), '*' * (2*i - 1), sep='')
for i in range(N-1, 1-1, -1):
    print(' ' * (N-i), '*' * (2*i - 1), sep='')
```
