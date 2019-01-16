# 2445 (별 찍기 - 8)

문제 링크: <https://www.acmicpc.net/problem/2445>

<br>

## Python3

```python
N = int(input())

for i in range(1, N+1):
    print('*' * i, ' ' * (2*(N-i)), '*' * i, sep='')
for i in range(1, N):
    print('*' * (N-i), ' ' * (2*i), '*' * (N-i), sep='')
```
