# 9461 (파도반 수열)

문제 링크: <https://www.acmicpc.net/problem/9461>  

<br>

## 접근방법

- 다이나믹 프로그래밍

규칙을 찾으면 쉽게 일반화 가능하다.

```python
D[n] = D[n-2] + D[n-3]
```

or

```python
D[n] = D[n-1] + D[n-5]
```

<br>

## Python3

Dynamic Programming (Bottom-Up)  

아래의 규칙을 활용하였다.

```python
D[n] = D[n-2] + D[n-3]
```

```python
def padovan_seq(n):
    d = [0] * (n+1) if n > 3 else [0] * 4
    d[1] = 1
    d[2] = 1
    d[3] = 1
    for i in range(4, n+1):
        d[i] = d[i-2] + d[i-3]
    return d[n]


T = int(input())
for _ in range(T):
    N = int(input())
    print(padovan_seq(N))
```
