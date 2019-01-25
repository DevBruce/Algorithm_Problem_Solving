# 11054 (가장 긴 바이토닉 부분 수열)

문제 링크: <https://www.acmicpc.net/problem/11054>  

<br>

## 접근방법

- 다이나믹 프로그래밍

- LIS (Longest Increasing Subsequence) 변형

<br>

## PyPy3

Dynamic Programming (Bottom-Up)  

해당 풀이는 Python3 로는 시간초과가 발생하여  
PyPy3 으로 제출

```python
def get_LIS_len(num, data):
    d = [1 for _ in range(num)]
    for i in range(num):
        for j in range(i):
            if data[j] < data[i] and d[i] < d[j] + 1:
                d[i] = d[j] + 1
    return max(d) if d else 1

def get_longest_decreasing_S_len(num, data):
    d = [1 for _ in range(num)]
    for i in range(num):
        for j in range(i):
            if data[j] > data[i] and d[i] < d[j] + 1:
                d[i] = d[j] + 1
    return max(d)

def get_longest_bitonic_S_len(num, data):
    d = [[1,1] for _ in range(num)]
    for i in range(num):
        d[i][0] = get_LIS_len(i+1, data[:i+1])
        d[i][1] = get_longest_decreasing_S_len(num-i, data[i:])
    dp = map(lambda x:sum(x)-1, d)
    return max(dp)


N = int(input())
A = list(map(int, input().split()))
print(get_longest_bitonic_S_len(N, A))
```
