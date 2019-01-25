# 2579 (계단 오르기)

문제 링크: <https://www.acmicpc.net/problem/2579>  

<br>

## 접근방법

- 다이나믹 프로그래밍

<br>

계단의 점수 X = x<sub>1</sub>, x<sub>2</sub> , . . . , x<sub>n-1</sub>, x<sub>n</sub>  이 있을 때  
X[1] = x<sub>1</sub>  
X[2] = x<sub>2</sub>  
. . .  
X[n] = x<sub>n</sub>
가 성립하고  

`D[n]` 을 n 번째 계단을 밟았을 때의 최대점수로 정의한다.  

이럴 경우 두 가지 경우로 나누어진다.  

**i )** n 번째 계단을 1번 연속 밟은 경우  

- n-1 번째 계단은 밟지 않는다.  

- n-2 번째 계단을 밟는다.

따라서 아래와 같은 식이 성립한다.  

```python
D[n] = D[n-2] + X[n] 
```

<br>

**ii )** n 번째 계단을 2번 연속 밟은 경우

- n-1 번째 계단을 밟았다.

- n-2 번째 계단은 밟지 않는다.  

- n-3 번째 계단을 밟는다.

따라서 아래와 같은 식이 성립한다.  

```python
D[n] = D[n-3] + X[n] + X[n-1]
```

<br>

`D[n]` 은 위의 두가지 경우 중 큰 값이 된다.  
따라서 최종적으로는 아래와 같은 식이 성립하게 된다.  

```python
D[n] = max(D[n-2] + X[n], D[n-3] + X[n] + X[n-1])
```

<br>

## Python3

Dynamic Programming (Bottom-Up)

### \# 1

1 차원 풀이

```python
def get_max(num, data):
    d = data.copy()
    d[0] = data[0]
    d[1] = data[1] + data[0]
    d[2] = max(data[0]+data[2], data[1]+data[2])
    for i in range(3, num):
        d[i] = max(d[i-2]+data[i], d[i-3]+data[i-1]+data[i])
    return d[num-1]


n = int(input())
stair_score = list()
for _ in range(n):
    stair_score.append(int(input()))

print(get_max(n, stair_score))
```

### \# 2

2 차원 풀이

`arr[i][0]` : i 번째 계단을 1번 연속 밟은 경우  
`arr[i][1]` : i 번째 계단을 2번 연속 밟은 경우

```python
def get_max(num, data):
    arr = [[0,0] for _ in range(num)]
    arr[0][0] = data[0]
    arr[0][1] = 0
    arr[1][0] = data[1]
    arr[1][1] = data[0] + data[1]
    arr[2][0] = data[0] + data[2]
    arr[2][1] = data[1] + data[2]
    d = [0] * num
    d[0] = max(arr[0])
    d[1] = max(arr[1])
    d[2] = max(arr[2])
    for i in range(3, num):
        arr[i][0] = max(arr[i-2]) + data[i]
        arr[i][1] = max(arr[i-3]) + data[i] + data[i-1]
        d[i] = max(arr[i])
    return d[num-1]


n = int(input())
stair_score = list()
for _ in range(n):
    stair_score.append(int(input()))

print(get_max(n, stair_score))
```
