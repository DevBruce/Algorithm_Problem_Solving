# 1463 (1로 만들기)

문제 링크: <https://www.acmicpc.net/problem/1463>

<br>

## 접근방법

- 다이나믹 프로그래밍

<br>

`D[n]` 은 n 을 1 로 만드는 최소 연산횟수로 가정한다.  

`D[n]` 은 아래의 세가지 항목 중 최솟값에 해당한다.  

**i )** n 에서 빼기 1 을 먼저 하는 경우  

```python
D[n] = D[n-1] + 1
```

> `+1` 은 빼기 1 을 하는 연산 한번을 의미한다.

**ii )** n 이 3 의 배수이므로 3 을 먼저 나누는 경우  

```python
D[n] = D[n/3] + 1
```

> `+1` 은 나누기 3 을 하는 연산 한번을 의미한다.

**iii )** n 이 2 의 배수이므로 2 를 먼저 나누는 경우  

```python
D[n] = D[n/2] + 1
```

> `+1` 은 나누기 2 를 하는 연산 한번을 의미한다.

위 세가지 경우 중 가장 작은 값이 `D[n]` 이 될 수 있다.  

<br>

## 주의사항

리스트 인덱싱은 `int` 통해서만 가능하다.  
`/` 으로 나누기를 할 경우 `float` 형태가 반환되므로  
`//` (몫 구하기) 를 통해 정수를 할당하였다.  

<br>

## Python3

Dynamic Programming (Bottom-Up)

### \# 1

```python
def make_one(num):
    d = [-1, 0, 1]
    for i in range(3, num+1):
        cnt_min = d[i-1] + 1
        if i % 3 == 0 and d[i//3] + 1 < cnt_min:
            cnt_min = d[i//3] + 1
        elif i % 2 == 0 and d[i//2] + 1 < cnt_min:
            cnt_min = d[i//2] + 1
        d.append(cnt_min)
    return d[num]


N = int(input())
print(make_one(N))
```

### \# 2

```python
def make_one(num):
    d = [0] * (num+1) if num > 1 else [0, 0, 0]
    d[0] = 0
    d[1] = 0
    d[2] = 1
    for i in range(3, num+1):
        d[i] = d[i-1] + 1
        if i % 3 == 0 and d[i//3] + 1 < d[i]:
            d[i] = d[i//3] + 1
        elif i % 2 == 0 and d[i//2] + 1 < d[i]:
            d[i] = d[i//2] + 1
    return d[num]


N = int(input())
print(make_one(N))
```
