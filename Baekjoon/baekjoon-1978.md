# 1978 (소수 찾기)

문제 링크: <https://www.acmicpc.net/problem/1978>

<br>

## 접근방법

- 에라토스테네스의 체

<br>

## Python3

```python
def eratosthenes(n):
    e = [True for _ in range(n)]
    e[0] = False
    primes = list()
    for i in range(2, n+1):
        if e[i-1]:
            primes.append(i)
            for j in range(i*2, n+1, i):
                e[j-1] = False
    return primes



N = int(input())
nums = map(int, input().split())

primes = eratosthenes(1000)
result = 0
for n in nums:
    if n in primes: result += 1
print(result)
```
