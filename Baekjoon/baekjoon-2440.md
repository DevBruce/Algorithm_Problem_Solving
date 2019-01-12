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

for i in range(N, 1-1, -1):
    print('*' * i)
```

### \# 3

```python
N = int(input())

for i in reversed(range(1, N+1)):
    print('*' * i)
```

### \# 4

```python
N = int(input())

for i in range(1, N+1)[::-1]:
    print('*' * i)
```
