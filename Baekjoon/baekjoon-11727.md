# 11727 (2xn 타일링 2)

문제 링크: <https://www.acmicpc.net/problem/11727>

<br>

해당 문제의 조건에 2x1 과 2x2 타일로 채우는 방법의 수를 구하라고 되어있지만  
[11726 (2xn 타일링)](https://www.acmicpc.net/problem/11726) 문제와 동일하게 1x2 도 추가해줘야 문제해결이 된다.  

<br>

## 접근방법

- 다이나믹 프로그래밍

`D[N]` 은 2xn 타일을 2x1, 1x2, 2x2 타일로 채울 수 있는 방법의 수라고 가정한다.  

`D[N]` 을 채우는 경우의 수는 3가지로 분류할 수 있다.  

<br>

**i )** 타일의 끝을 2x1 한개로 채우는 경우

<img src="https://github.com/DevBruce/Algorithm_Problem_Solving/blob/master/Baekjoon/images/baekjoon-11727-tile01.png" width="400">  

<br>

**ii )** 타일의 끝을 1x2 두개로 채우는 경우

<img src="https://github.com/DevBruce/Algorithm_Problem_Solving/blob/master/Baekjoon/images/baekjoon-11727-tile02.png" width="400">  

<br>

**iii )** 타일의 끝을 2x2 한개로 채우는 경우

<img src="https://github.com/DevBruce/Algorithm_Problem_Solving/blob/master/Baekjoon/images/baekjoon-11727-tile03.png" width="400">  

<br>

따라서 결과는 다음과 같다.

```
D[N] = D[N-1] + D[N-2] + D[N-2]
```

```
D[N] = D[N-1] + 2 * D[N-2]
```

<br>

## 특이사항

`D[0]` 은 2x0 타일을 채우는 방법의 수를 의미하게 된다.  
`D[0]` 의 해는 없다.  
해당 문제의 경우, "해가 없다" 를 1개라고 할당할 경우 문제접근을 더욱  
간단하게 할 수 있다.  

<br>

## Python3

Dynamic Programming (Bottom-Up)

```python
def tile_cnt(num):
    dp = [1, 1]
    for i in range(2, num+1):
        dp.append(dp[i-1] + 2 * dp[i-2])
    return dp[num]


n = int(input())
print(tile_cnt(n) % 10007)
```
