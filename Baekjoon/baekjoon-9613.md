# 9613 (GCD 합)

문제 링크: <https://www.acmicpc.net/problem/9613>  

<br>

## 접근방법

유클리드 호제법을 통해 GCD (최대공약수) 를 구하였다.  

참고 : [DevBruce's Blog - [Algorithm] GCD / LCM / Euclidean Algorithm](https://devbruce.github.io/algorithm/alg-02-gcd/)

<br>

## Python3

```python
def GCD(a, b):
    num, div = max(a,b), min(a,b)
    while num % div:
        num, div = div, num % div
    return div


t = int(input())
for _ in range(t):
    n, *data = map(int, input().split())
    result = 0
    for i in range(n-1):
        for j in range(i+1, n):
            result += GCD(data[i], data[j])
    print(result)
```
