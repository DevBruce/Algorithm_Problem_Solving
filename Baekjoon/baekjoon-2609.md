# 2609 (최대공약수와 최소공배수)

문제 링크: <https://www.acmicpc.net/problem/2609>  

<br>

## 접근방법

유클리드 호제법을 통해 최대공약수 (GCD) 를 구한 뒤,  
최대공약수를 통해 최소공배수 (LCM) 을 구하였다.  

참고 : [DevBruce's Blog - [Algorithm] GCD / LCM / Euclidean Algorithm](https://devbruce.github.io/algorithm/alg-02-gcd/)

<br>

## Python3

```python
def GCD(a, b):
    num, div = max(a,b), min(a,b)
    while num % div:
        num, div = div, num % div
    return div

def LCM(a, b):
    return int(a * b / GCD(a, b))


x, y = map(int, input().split())
print(GCD(x, y), LCM(x, y), sep='\n')
```
