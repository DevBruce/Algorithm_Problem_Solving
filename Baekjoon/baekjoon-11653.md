# 11653 (소인수분해)

문제 링크: <https://www.acmicpc.net/problem/11653>

<br>

## Python3

```python
def prime_factorization(num): 
    for d in range(2, int(num ** 0.5)+1):
        while num % d == 0:
            print(d)
            num //= d
    if num != 1:
        print(num)


N = int(input())
prime_factorization(N)
```
