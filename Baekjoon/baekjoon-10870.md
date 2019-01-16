# 10870 (피보나치 수 5)

문제 링크: <https://www.acmicpc.net/problem/10870>

<br>

## Python3

Dynamic Programming (Bottom-Up)

```python
def fibo(n):
    d = [0, 1]
    for i in range(2, n+1):
        d.append(d[i-1] + d[i-2])
    return d[n]


n = int(input())
print(fibo(n))
```
