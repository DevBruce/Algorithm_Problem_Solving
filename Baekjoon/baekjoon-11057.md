# 11057 (오르막 수)

문제 링크: <https://www.acmicpc.net/problem/11057>

<br>

## 접근방법

- 다이나믹 프로그래밍

`D[N][L]` 은 자릿수가 N 이며 이며 N번째 자릿수가 L 인 경우  
오르막 수의 갯수라고 가정한다.  

> 이에따라 문제에서 원하는 자릿수가 N인 오르막 수의 갯수는  
> `D[N][0] + D[N][1] + D[N][2] + . . . + D[N][9]` 이다.

<br>

N번째 자릿수가 L 인 경우  
N-1번째 자릿수는 L 보다 작거나 같은 수들이 가능하다.  
(0 ~ L 이 이에 해당)

| N-1번째 자리       | N번째 자리 |
|--------------------|------------|
| 0, 1, 2, . . . , L | L          |

<br>

따라서 아래와 같은 형태가 된다.

```
D[N][L] = D[N-1][0] + D[N-1][1] + D[N-1][2] + . . . + D[N-1][L]
```

<br>

## Python3

Dynamic Programming (Bottom-Up)

```python
def get_asc_num_cnt(num):
    dp = [[0 for _ in range(10)] for _ in range(num+1)]
    for l in range(9+1):
        dp[1][l] = 1

    for n in range(2, num+1):
        for l in range(9+1):
            for k in range(l+1):
                dp[n][l] += dp[n-1][k]

    return sum(dp[num])


N = int(input())
print(get_asc_num_cnt(N) % 10007)
```
