# 2133 (타일 채우기)

문제 링크: <https://www.acmicpc.net/problem/2133>  

<br>

## 접근방법

- 다이나믹 프로그래밍

<br>

`D[n]` 은 (3 x n) 타일을 (1 x 2), (2 x 1) 두 종류의 타일로 채우는 방법의 가짓수라고 정의한다.  

이 때 n 이 홀수일 경우 `D[n]` 은 0 됨을 알 수 있다.  

n 이 짝수일 때 맨 끝에 올 수 있는 타일의 방법은 다음과 같다.  

<img src="https://github.com/DevBruce/Algorithm_Problem_Solving/blob/master/Baekjoon/images/baekjoon-2133-tile01.png" width="420">  

<br>

그리고 `n >= 4` 의 경우  
타일의 끝에 경우 다음과 같은 형태의 타일이 추가로 올 수 있다.  

<img src="https://github.com/DevBruce/Algorithm_Problem_Solving/blob/master/Baekjoon/images/baekjoon-2133-tile02.png" width="430">  

<br>

`n >= 6` 의 경우  
타일의 끝에 다음과 같은 형태의 타일이 추가로 올 수 있다.  

<img src="https://github.com/DevBruce/Algorithm_Problem_Solving/blob/master/Baekjoon/images/baekjoon-2133-tile03.png" width="440">  

<br>

위와 같은 규칙에 따라  
n (`n >= 4`) 이 2 커질수록 끝에 올 수 있는 타일의 수가 계속해서 2 가지 추가된다.  

<br><br>

## 특이사항

- `D[0] = 1` 로 초깃값 설정 가능

<br><br>

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
