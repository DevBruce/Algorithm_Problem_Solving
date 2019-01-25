# 11055 (가장 큰 증가 부분 수열)

문제 링크: <https://www.acmicpc.net/problem/11055>  

<br>

## 접근방법

- 다이나믹 프로그래밍

- LIS (Longest Increasing Subsequence) 변형

<br>

## Python3

Dynamic Programming (Bottom-Up)

```python
def get_greatest_IS_val(num, data):
    d = data.copy()
    for i in range(num):
        for j in range(i):
            if data[j] < data[i] and d[i] < d[j] + data[i]:
                d[i] = d[j] + data[i]
    return max(d)


N = int(input())
A = list(map(int, input().split()))
print(get_greatest_IS_val(N, A))
```
