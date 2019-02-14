# 10872 (팩토리얼)

문제 링크: <https://www.acmicpc.net/problem/10872>

<br>

## Python3

```python
def factorial(num):
    result = 1
    for i in range(2, num+1):
        result *= i
    return result


N = int(input())
print(factorial(N))
```
