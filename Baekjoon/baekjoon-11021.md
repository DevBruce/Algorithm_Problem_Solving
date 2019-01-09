# 11021 (A+B - 7)

문제 링크: <https://www.acmicpc.net/problem/11021>

<br>

## Python3

```python
T = int(input())

for n in range(T):
    tmp = input().split()
    A = int(tmp[0])
    B = int(tmp[1])
    print(f'Case #{n+1}: {A + B}')
```
