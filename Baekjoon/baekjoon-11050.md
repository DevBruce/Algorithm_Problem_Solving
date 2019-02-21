# 11050 (이항 계수 1)

문제 링크: <https://www.acmicpc.net/problem/11050>

<br>

## Python3


```python
def binomial_coefficient(n, k):
    a, b = 1, 1
    for i in range(N, N-K, -1):
        a *= i
    for i in range(1, K+1):
        b *= i
    return a//b


N, K = map(int, input().split())
print(binomial_coefficient(N, K))
```
