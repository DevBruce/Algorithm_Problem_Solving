# 9465 (스티커)

문제 링크: <https://www.acmicpc.net/problem/9465>  

<br>

## 접근방법

- 다이나믹 프로그래밍

<br>

해당 문제의 경우는 스티커를 떼어내는 순서가 정해져 있지 않다.  
따라서 임의로 가장 오른쪽 열부터 제거하는 것으로 정한다.  
`D[n][m]` 은 n 번째 열을 m 의 방법으로 뜯어내는 것으로 정의한다.  
`S[x][y]` 는 x 열의 y 행의 카드 점수라고 정의한다.  

n 열의 스티커를 제거하는 방법 m 은 3가지로 분류할 수 있다.  

- 1, 2 행 스티커 그대로 두기 (`m = 0`)

- 1 행 스티커 뜯기 (`m = 1`)

- 2 행 스티커 뜯기 (`m = 2`)

<br><br>

**i )** n 열의 1, 2 행 스티커 그대로 두기 (`D[n][0]`)  

이 경우 n-1 열은 다음과 같은 방법을 택할 수 있다.  

- 1, 2 행 스티커 그대로 두기 (`D[n-1][0]`)

- 1 행 스티커 뜯기 (`D[n-1][1]`)

- 2 행 스티커 뜯기 (`D[n-1][2]`)

따라서 위의 3 가지 경우 중 가장 큰 값이 `D[n][0]` 에 해당한다.  

```python
D[n][0] = max(D[n-1][0], D[n-1][1], D[n-1][2])
```

<br>

**ii )** n 열의 1 행 스티커 뜯기 (`D[n][1]`)  

이 경우 n-1 열이 선택할 수 있는 방법은 다음과 같다.  

- 1, 2 행 스티커 그대로 두기 (`D[n-1][0]`)  

- 2 행 스티커 뜯기 (`D[n-1][2]`)  

따라서 아래와 같은 식이 성립한다.  

```python
D[n][1] = max(D[n-1][0], D[n-1][2]) + S[n][1]
```

<br>

**iii )** n 열의 2 행 스티커 뜯기 (`D[n][2]`)   

이 경우 n-1 열이 선택할 수 있는 방법은 다음과 같다.  

- 1, 2 행 스티커 그대로 두기 (`D[n-1][0]`)  

- 1 행 스티커 뜯기 (`D[n-1][1]`)  

따라서 아래와 같은 식이 성립한다.  

```python
D[n][2] = max(D[n-1][0], D[n-1][1]) + S[n][2]
```

<br>

## Python3

Dynamic Programming (Bottom-Up)

```python
def get_max(num, data):
    score_arr = [[0, 0] for _ in range(num)]
    for idx, score in enumerate(data):
        score_arr[idx % num][idx // num] = score
    
    d = [[0, 0, 0] for _ in range(num)]
    d[0][0] = 0
    d[0][1] = score_arr[0][0]
    d[0][2] = score_arr[0][1]
    
    for i in range(1, num):
        d[i][0] = max(d[i-1])
        d[i][1] = max(d[i-1][0], d[i-1][2]) + score_arr[i][0]
        d[i][2] = max(d[i-1][0], d[i-1][1]) + score_arr[i][1]
        
    max_score = max(d[num-1])
    return max_score


T = int(input())
for _ in range(T):
    n = int(input())
    cards = list(map(int, input().split()))
    cards.extend(map(int, input().split()))
    print(get_max(n, cards))
```
