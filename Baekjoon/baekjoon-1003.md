# 1003 (피보나치 함수)

문제 링크: <https://www.acmicpc.net/problem/1003>

<br>

## 접근방법

해당 문제는 단순하게 피보나치 수열에서 특정 인덱스의 값을 구하는 것이 아니다.  
문제에서는 재귀함수로 구성된 피보나치 함수를 제시하고 있으며,    
이 때 `f(0)` 과 `f(1)` 이 호출되는 횟수를 구하는 것이다.  

`f(0)` 과 `f(1)` 의 호출 횟수를 직접 구해보면 아래와 같다.  

<br>

| N    | 0 | 1 | 2 | 3 | 4 | 5 | 6 | . . . |
|------|---|---|---|---|---|---|---|-------|
| f(0) | 1 | 0 | 1 | 1 | 2 | 3 | 5 | . . . |
| f(1) | 0 | 1 | 1 | 2 | 3 | 5 | 8 | . . . |

<br>

`f(0)` 과 `f(1)` 의 호출 횟수가 피보나치 수열로 이루어지는 것을 확인할 수 있다.  

<br>

## Python3

Dynamic Programming (Bottom-Up)

```python
def fibo_call_zero_one_cnt(n):
    zero_cnt = [1, 0]
    one_cnt = [0, 1]
    for i in range(2, n+1):
        zero_cnt.append(zero_cnt[i-1] + zero_cnt[i-2])
        one_cnt.append(one_cnt[i-1] + one_cnt[i-2])
    return zero_cnt[n], one_cnt[n]


T = int(input())

for _ in range(T):
    N = int(input())
    result = fibo_call_zero_one_cnt(N)
    print(f'{result[0]} {result[1]}')
```
