# 1463 (1로 만들기)

문제 링크: <https://www.acmicpc.net/problem/1463>

<br>

## 접근방법

- 다이나믹 프로그래밍

`D[N]` 은 N을 1로 만드는 최소 연산횟수로 가정한다.  

`D[N]` 은 아래의 세가지 항목 중 최솟값에 해당한다.  

- `D[N-1] + 1`
- `D[N/3] + 1` (3 으로 나누어질 경우)  
- `D[N/2] + 1` (2 로 나누어질 경우)

<br>

## 주의사항

리스트 인덱싱은 `int` 통해서만 가능하다.  
`/` 으로 나누기를 할 경우 `float` 형태가 반환되므로  
`//` (몫 구하기) 를 통해 정수를 할당하였다.  

<br>

## Python3

Dynamic Programming (Bottom-Up)

```python
def make_one(num):
    dp = [-1, 0, 1]
    for i in range(3, num+1):
        cnt_min = dp[i-1] + 1
        if i % 3 == 0 and dp[i//3] + 1 < cnt_min:
            cnt_min = dp[i//3] + 1
        elif i % 2 == 0 and dp[i//2] + 1 < cnt_min:
            cnt_min = dp[i//2] + 1
        dp.append(cnt_min)
    return dp[num]


N = int(input())
print(make_one(N))
```