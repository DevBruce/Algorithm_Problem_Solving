# 2747 (피보나치 수)

문제 링크: <https://www.acmicpc.net/problem/2747>

<br>

## Python3

Dynamic Programming (Bottom-Up)

```python
def fibo(n):
    dp = [0, 1]
    for i in range(2, n+1):
        dp.append(dp[i-1] + dp[i-2])
    return dp[n]

n = int(input())
print(fibo(n))
```
