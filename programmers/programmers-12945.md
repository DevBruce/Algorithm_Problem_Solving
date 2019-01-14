# 피보나치 수

문제 링크: <https://programmers.co.kr/learn/courses/30/lessons/12945>  

- 연습문제

- 다이나믹 프로그래밍

<br>

## Python3

Dynamic Programming (Bottom-Up)

```python
def solution(n):
    dp = [0, 1]
    for i in range(2, n+1):
        dp.append(dp[i-1] + dp[i-2])
    return dp[n] % 1234567
```
