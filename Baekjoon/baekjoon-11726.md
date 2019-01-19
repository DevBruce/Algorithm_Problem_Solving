# 11726 (2xn 타일링)

문제 링크: <https://www.acmicpc.net/problem/11726>

<br>

## 접근방법

- 다이나믹 프로그래밍

<br>

`D[n]` 은 2xn 타일을 2x1 과 1x2 타일로 채울 수 있는 방법의 수라고 가정한다.  

`D[n]` 을 채우는 경우의 수는 두가지로 분류할 수 있다.  

<br>

**i )** 타일의 끝을 2x1 한개로 채우는 경우

<img src="https://github.com/DevBruce/Algorithm_Problem_Solving/blob/master/Baekjoon/images/baekjoon-11726-tile01.png" width="400">  

<br>

**ii )** 타일의 끝을 1x2 두개로 채우는 경우

<img src="https://github.com/DevBruce/Algorithm_Problem_Solving/blob/master/Baekjoon/images/baekjoon-11726-tile02.png" width="400">  

<br>

따라서 `D[n] = D[n-1] + D[n-2]` 임을 알 수 있다.  

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
    d = [1, 1]
    for i in range(2, num+1):
        d.append(d[i-1] + d[i-2])
    return d[num]


n = int(input())
print(tile_cnt(n) % 10007)
```
