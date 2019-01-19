# 2156 (포도주 시식)

문제 링크: <https://www.acmicpc.net/problem/2156>  

<br>

## 접근방법

- 다이나믹 프로그래밍

<br>

`D[n][s]` 는 n 번째 포도주를 연속 s 번째 마시는 경우로,  
`W[n]` 은 n 번째 포도주의 양이라고 정의한다.

이에따라 위의 문제는 3가지 경우로 나뉜다.  

<br>

**i )** s 가 0 인 경우 (`D[n][0]`)  

이 경우는 n 번째 포도주를 마시지 않는다.  

n-1 번째 포도주는  

- 연속으로 0 번째 마신 경우 (`D[n-1][0]`)  
- 연속으로 1 번째 마신 경우 (`D[n-1][1]`)  
- 연속으로 2 번째 마신 경우 (`D[n-1][2]`)  

3 가지 경우가 모두 가능하다.  
그러므로 위의 3가지 경우 중 가장 큰 값이 `D[n][0]` 이 된다.  

```python
D[n][0] = max(D[n-1][0], D[n-1][1], D[n-1][2])
```

<br>

**ii )** s 가 1 인 경우 (`D[n][1]`)  

이 경우는 n 번째 포도주를 1번째 연속 마신 것을 의미한다.  

n-1 번째 포도주는  

- 연속으로 0 번째 마신 경우 (`D[n-1][0]`)  

한가지 경우가 가능하다.  
따라서 아래의 식이 성립한다.  

```python
D[n][1] = D[n-1][0] + W[n]
```

<br>

**iii )** s 가 2 인 경우 (`D[n][2]`)  

이 경우는 n 번째 포도주를 2번째 연속 마신 것을 의미한다.  

n-1 번째 포도주는  

- 연속으로 1 번째 마신 경우 (`D[n-1][1]`)  

한가지 경우가 가능하다.  
따라서 아래의 식이 성립한다.  

```python
D[n][2] = D[n-1][1] + W[n]
```

<br>

## Python3

Dynamic Programming (Bottom-Up)

```python
def get_max(num, data):
    d = [[0, 0, 0] for _ in range(num)]
    d[0][0] = 0
    d[0][1] = data[0]
    d[0][2] = 0
    
    for i in range(1, num):
        d[i][0] = max(d[i-1])
        d[i][1] = d[i-1][0] + data[i]
        d[i][2] = d[i-1][1] + data[i]
        
    max_wine = max(d[num-1])
    return max_wine


n = int(input())
wines = list()
for _ in range(n):
    wines.append(int(input()))
print(get_max(n, wines))
```
