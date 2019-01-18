# 1912 (연속합)

문제 링크: <https://www.acmicpc.net/problem/1912>  

<br>

## 접근방법

- 다이나믹 프로그래밍

<br>

수열 X = x<sub>1</sub>, x<sub>2</sub> , . . . , x<sub>n-1</sub>, x<sub>n</sub>  이 있을 때  
X[1] = x<sub>1</sub>  
X[2] = x<sub>2</sub>  
. . .  
X[n] = x<sub>n</sub>
가 성립하고  

`D[n]` 은 마지막 수가 `X[n]` 인 연속합 중 가장 큰 값이라고 가정한다.  
이에따라 두가지 경우로 나눌 수 있다.  

<br>

**i )** `X[n]` 이 `D[n-1]` 에 포함된 연속합인 경우  

이 경우에는 `D[n] = D[n-1] + X[n]` 이 성립하게 된다.  

<br>

**ii )** `X[n]` 이 `D[n-1]` 에 포함되지 않은 경우  

이 경우에는 `D[n] = X[n]` 이 성립하게 된다.  

위의 두가지 경우 중 큰 값이 `D[n]` 에 해당하게 된다.  
따라서 아래와 같이 나타낼 수 있다.

```python
D[n] = max(D[n-1] + X[n], X[n])
```

<br>

## Python3

Dynamic Programming (Bottom-Up)

```python
def get_max(num, data):
    d = data.copy()
    for i in range(1, num):
        d[i] = max(d[i-1] + data[i], data[i])
    return max(d)


n = int(input())
raw = list(map(int, input().split()))
print(get_max(n, raw))
```
