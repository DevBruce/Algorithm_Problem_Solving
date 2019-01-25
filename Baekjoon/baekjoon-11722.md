# 11722 (가장 긴 감소하는 부분 수열)

문제 링크: <https://www.acmicpc.net/problem/11722>  

<br>

## 접근방법

- 다이나믹 프로그래밍

- LIS (Longest Increasing Subsequence) 변형

<br>

## Python3

Dynamic Programming (Bottom-Up)

```python
def get_longest_decreasing_S_len(num, data):
    d = [1 for _ in range(num)]
    for i in range(num):
        for j in range(i):
            if data[j] > data[i] and d[i] < d[j] + 1:
                d[i] = d[j] + 1
    return max(d)


N = int(input())
A = list(map(int, input().split()))
print(get_longest_decreasing_S_len(N, A))
```
