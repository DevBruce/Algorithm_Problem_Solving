# 9020 (골드바흐의 추측)

문제 링크: <https://www.acmicpc.net/problem/9020>  

<br>

## 접근방법

- 에라토스테네스의 체

<br>

## Python3

```python
import sys
sys_input = sys.stdin.readline


def eratosthenes_bool(n):
    e = [True for _ in range(n)]
    e[0] = False
    for i in range(2, n+1):
        if e[i-1]:
            for j in range(i*2, n+1, i):
                e[j-1] = False
    return e


is_prime_list = eratosthenes_bool(10000)
T = int(sys_input())
for _ in range(T):
    n = int(sys_input())
    partition = list()
    for a in range(2, n+1):
        b = n - a
        if is_prime_list[a-1] and is_prime_list[b-1]:
            diff = b - a if b - a >= 0 else a - b
            partition.append((a, b, diff))
    result = min(partition, key=lambda x : x[2])
    print(*result[:1+1])
```
