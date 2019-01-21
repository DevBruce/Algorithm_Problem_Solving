# 11052 (카드 구매하기)

문제 링크: <https://www.acmicpc.net/problem/11052>

<br>

## 접근방법

- 다이나믹 프로그래밍

`D[n]` 은 카드 n 개를 사는 최대비용이라고 정의한다.  

카드 n 개를 사는 방법은 다음과 같다.

x<sub>1</sub> + x<sub>2</sub> + x<sub>3</sub> + . . . + x<sub>i-2</sub> + x<sub>i-1</sub> + x<sub>i</sub> = n  

x<sub>i</sub> = 1 인 경우,  
(x<sub>1</sub> + x<sub>2</sub> + x<sub>3</sub> + . . . + x<sub>i-2</sub> + x<sub>i-1</sub>) + 1 = n 가 된다.  

이 때 카드 1개를 살 때의 비용은 P<sub>1</sub> 에 해당하며  
(x<sub>1</sub> + x<sub>2</sub> + x<sub>3</sub> + . . . + x<sub>i-2</sub> + x<sub>i-1</sub>) = n - 1 이며    
n-1 개의 카드를 사는 최대비용은 `D[n-1]` 이 된다.  

즉 D[n] = D[n-1] + P<sub>1</sub> 이 성립하게 된다.  

이를 반복하면 아래와 같이 나타나게 된다.  

D[n] = D[n-1] + P<sub>1</sub>  
D[n] = D[n-2] + P<sub>2</sub>  
D[n] = D[n-3] + P<sub>3</sub>  
. . .  
D[n] = D[n-(n-1)] + P<sub>n-1</sub>  
D[n] = D[0] + P<sub>n</sub>  

위의 값 중에서 최대값이 바로 D[n] 이 된다.  

<br>

### Example

D[3] 을 구하고자 할 경우  

D[2] + P<sub>1</sub>  
D[1] + P<sub>2</sub>  
D[0] + P<sub>3</sub>  

위의 세가지 값 중 최대값이 D[3] 의 값이 된다.  

<br>

## Python3


```python
def max_price(num, data):
    d = [0] * (num+1)
    for n in range(1, num+1):
        for i in range(1, n+1):
            d[n] = max(d[n], d[n-i] + data[i-1])
    return d[num]


N = int(input())
prices = [int(s) for s in input().split()]
print(max_price(N, prices))
```
