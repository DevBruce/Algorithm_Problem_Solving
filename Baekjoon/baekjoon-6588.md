# 6588 (골드바흐의 추측)

문제 링크: <https://www.acmicpc.net/problem/6588>

<br>

## 접근방법

- 에라토스테네스의 체

<br>

## 특이사항

시간초과 문제를 해결하기위해서  
`input()` 대신 `sys.stdin.readline` 을 활용한다.  

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


is_prime_list = eratosthenes_bool(1000000)
while True:
    n = int(sys_input())
    if n == 0: break
    for a in range(2, n+1):
        b = n - a
        if is_prime_list[a-1] and is_prime_list[b-1]:
            print(f'{n} = {a} + {b}')
            break
    else:
        print("Goldbach's conjecture is wrong.")
```
