# 2193 (이친수)

문제 링크: <https://www.acmicpc.net/problem/2193>

<br>

## 접근방법 1

- 다이나믹 프로그래밍

<br>

해당 문제는 n 자리의 이친수 갯수를 구하는 것이다.  

`D[n][v]` 은 n 번째 자릿수가 v 인 n 자리의 이친수 갯수라고 정의한다.  

v 는 두가지 경우로 나눌 수 있다.  

<br>

**i )** v = 0 (`D[n][0]`)  

위의 의미는 n번째 자릿수 v 가 0 인 n 자리 이친수의 갯수를 의미한다.  
이 때 n-1 은 다음과 같은 경우가 올 수 있다.  

- `D[n-1][0]`

- `D[n-1][1]`

따라서 다음과 같은 식이 성립한다.  

```python
D[n][0] = D[n-1][0] + D[n-1][1]
```

<br>

**ii )** v = 1 (`D[n][1]`)  

위의 의미는 n번째 자릿수 v 가 1 인 n 자리 이친수의 갯수를 의미한다.  
이 때 n-1 은 다음과 같은 경우가 올 수 있다.  

- `D[n-1][0]`

따라서 다음과 같은 식이 성립한다.  

```python
D[n][1] = D[n-1][0]
```

<br>

## 접근방법 2

- 다이나믹 프로그래밍

<br>

해당 문제는 n 자리의 이친수 갯수를 구하는 것이다.  

D[n] 을 n 자리의 이친수 갯수라고 정의한 뒤  
케이스를 두가지로 분류한다.  

<br>

**i )** n 번째 자리가 0인 경우

이 경우에 n-1 번째 자리에는 0과 1 모두 올 수 있다.  
따라서 n 번째 자리가 0인 경우에는  
D[n-1] 과 동일하다.  

| n-1 번째 자리 | n 번째 자리 |
|--------------|------------|
| 0 또는 1     | 0          |
| D[n-1]     |            |

따라서 이 경우의 이친수 갯수는 `D[n-1]` 이다.

<br>

**ii )** n 번째 자리가 1인 경우

이 경우에 n-1 번째 자리에는 0 만 올 수 있다.  
(조건에 따라 1이 연속적으로 나올 수 없다.)  
그리고 n-2 번째 자리에는 0과 1 모두 올 수 있다.  

| n-2 번째 자리 | n-1 번째 자리 | n 번째 자리 |
|--------------|--------------|------------|
| 0 또는 1     | 0            | 1          |
| D[n-2]     | 고정         |            |

따라서 이 경우의 이친수 갯수는 `D[n-2]` 이다.

<br>

n 자리 이친수의 갯수는 두 가지 케이스를 더한 것과 같으므로  
`D[n] = D[n-1] + D[n-2]` 의 형태가 된다.  

<br>

## Python3

### 접근방법 1

Dynamic Programming (Bottom-Up)

```python
def get_cnt(num):
    d = [[0, 0] for _ in range(num)]
    d[0][0] = 0
    d[0][1] = 1
    for i in range(1, num):
        d[i][0] = d[i-1][0] + d[i-1][1]
        d[i][1] = d[i-1][0]
    return sum(d[num-1])


N = int(input())
print(get_cnt(N))
```

<br>

### 접근방법 2

Dynamic Programming (Bottom-Up)

#### \# 1

```python
def get_cnt(num):
    d = [1, 1]
    for i in range(2, num):
        d.append(d[i-1] + d[i-2])
    return d[num-1]


N = int(input())
print(get_cnt(N))
```

#### \# 2

```python
def get_cnt(num):
    d = [0] * num if num > 1 else [0, 0]
    d[0] = 1
    d[1] = 1
    for i in range(2, num):
        d[i] = d[i-1] + d[i-2]
    return d[num-1]


N = int(input())
print(get_cnt(N))
```
