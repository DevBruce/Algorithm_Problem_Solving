# 2440 (별 찍기 - 3)

문제 링크: <https://www.acmicpc.net/problem/2440>

<br>

## Python3

### \# 1

```python
N = int(input())

for i in range(N):
    print('*' * (N-i))
```

### \# 2

```python
N = int(input())

for i in reversed(range(1, N+1)):
    print('*' * i)
```
