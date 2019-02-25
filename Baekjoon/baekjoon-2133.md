# 2133 (타일 채우기)

문제 링크: <https://www.acmicpc.net/problem/2133>  

<br>

## 접근방법

- 다이나믹 프로그래밍

<br>

## 특이사항

- `D[0] = 1` 로 가능

<br>

## Python3

Dynamic Programming (Bottom-Up)

```python
def get_cnt(n):
    d = [0] * (n+1)
    d[0] = 1
    for i in range(2, n+1, 2):
        d[i] = d[i-2] * 3
        for j in range(4, i+1, 2):
            d[i] += d[i-j] * 2
    return d[n]


N = int(input())
print(get_cnt(N))
```
