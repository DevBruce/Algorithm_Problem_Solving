# 11053 (가장 긴 증가하는 부분 수열)

문제 링크: <https://www.acmicpc.net/problem/11053>  

<br>

## 접근방법

- 다이나믹 프로그래밍

- LIS (Longest Increasing Subsequence)

<br>

수열 X = x<sub>1</sub>, x<sub>2</sub> , . . . , x<sub>n-1</sub>, x<sub>n</sub>  이 있을 때  
X[1] = x<sub>1</sub>  
X[2] = x<sub>2</sub>  
. . .  
X[n] = x<sub>n</sub>
가 성립하고  

`D[n]` 은  
**X[n] 을 마지막으로 하는 가장 긴 증가하는 부분 수열 (LIS) 의 길이**  
라고 정의한다.  

n 보다 작은 인덱스 m 을 정의하고 다음과 같은 조건이 있을 때  

- `X[m] < X[n]`

- `D[m] + 1 > D[n]`

X[n] 을 마지막으로 하는 LIS 의 길이 (`D[n]`)는  
X[m] 을 마지막으로 하는 LIS 의 길이 (`D[m]`) + 1 이 된다.  

```python
D[n] = D[m] + 1
```

<br>

## Python3

Dynamic Programming (Bottom-Up)

```python
def get_LIS_len(num, data):
    d = [1 for _ in range(num)]
    for i in range(num):
        for j in range(i):
            if data[j] < data[i] and d[i] < d[j] + 1:
                d[i] = d[j] + 1
    return max(d)


N = int(input())
A = list(map(int, input().split()))
print(get_LIS_len(N, A))
```
