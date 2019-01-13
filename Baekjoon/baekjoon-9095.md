# 9095 (1,2,3 더하기)

문제 링크: <https://www.acmicpc.net/problem/9095>  

<br>

## 접근방법

- 다이나믹 프로그래밍

`D[N]` 은 N을 1, 2, 3 의 합으로 나타날 수 있는 방법의 갯수라고 가정한다.  

N 을 식으로 표현하면 다음과 같다.

x<sub>1</sub> + x<sub>2</sub> + x<sub>3</sub> + . . . + x<sub>i-1</sub> + x<sub>i</sub> = N  

이 때 x<sub>i</sub> 가 될 수 있는 경우의 수는 3가지이다.  

<br>

**i )** x<sub>i</sub> = 1

x<sub>1</sub> + x<sub>2</sub> + x<sub>3</sub> + . . . x<sub>i-1</sub> = N - 1  

\>\>\> `D[N-1]`  

<br>

**ii )** x<sub>i</sub> = 2

x<sub>1</sub> + x<sub>2</sub> + x<sub>3</sub> + . . . x<sub>i-1</sub> = N - 2

\>\>\> `D[N-2]`  

<br>

**iii )** x<sub>i</sub> = 3

x<sub>1</sub> + x<sub>2</sub> + x<sub>3</sub> + . . . x<sub>i-1</sub> = N - 3

\>\>\> `D[N-3]`  

<br>

이에따라 `D[N] = D[N-1] + D[N-2] + D[N-3]` 임을 알 수 있다.  

<br>

## 특이사항

`D[0]` 은 0을 1, 2, 3 세가지 수의 더하기로 나타내는 방법의 수를 의미하게 된다.  
`D[0]` 의 해는 없다.  
해당 문제의 경우, "해가 없다" 를 1개라고 할당할 경우 문제접근을 더욱  
간단하게 할 수 있다.  

<br>

## Python3

Dynamic Programming (Bottom-Up)

```python
def get_cnt(num):
    dp = [1, 1, 2]
    for i in range(3, num+1):
        dp.append(dp[i-1] + dp[i-2] + dp[i-3])
    return dp[n]


T = int(input())

for _ in range(T):
    n = int(input())
    print(get_cnt(n))
```
