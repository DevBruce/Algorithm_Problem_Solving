# 10844 (쉬운 계단 수)

문제 링크: <https://www.acmicpc.net/problem/10844>

<br>

## 접근방법

- 다이나믹 프로그래밍

`D[n][k]` 를 끝자리 (n 번째 자릿수) 가 k 인 n 자리 계단수의 갯수라고 정의한다.  

<br>

**i )** `D[n][9]` 의 경우  

n 번째 자릿수가 9 가 되므로  

n - 1 번째 자릿수는 8 만 올 수 있다.  

<br>

**ii )** `D[n][0]` 의 경우  

n 번째 자릿수가 0 이 되므로  

n - 1 번째 자릿수는 1 만 올 수 있다.  

<br>

**iii )** k 가 0 또는 9 를 제외한 경우  

n 번째 자릿수가 k 일 때

n - 1 번째 자릿수는 k-1 또는 k+1 이 가능하다.  

<br>

위의 세가지 경우들을 일반화 시키면 다음과 같다.  

```python
if k == 0:
    d[n][k] = d[n-1][1]
elif k == 9:
    d[n][k] = d[n-1][8]
else:
    d[n][k] = d[n-1][k-1] + d[n-1][k+1]
```

<br><br>

## 특이사항

- `d[1][0]` (1 자리 계단수이며 0 인 경우) 는 불가능하므로 0 이 된다.

- 정답을 1000000000 로 나눈 나머지를 출력

<br><br>

## Python3

Dynamic Programming (Bottom-Up)

```python
def get_cnt(n):
    d = [([0] * 10) for _ in range(n+1)]
    d[1] = [1] * 10
    d[1][0] = 0
    for i in range(2, n+1):
        for j in range(10):
            if j == 0:
                d[i][j] = d[i-1][1]
            elif j == 9:
                d[i][j] = d[i-1][8]
            else:
                d[i][j] = d[i-1][j-1] + d[i-1][j+1]
    return sum(d[n])


N = int(input())
print(get_cnt(N) % 1000000000)
```
