# 1699 (제곱수의 합)

문제 링크: <https://www.acmicpc.net/problem/1699>

<br>

## 접근방법

- 다이나믹 프로그래밍

<br>

`D[n]` 은 n 을 제곱수의 합으로 나타낼 때 항의갯수가 최소일 때 항의 갯수로 정의한다.

정수 n 을 아래와 같이 정의할 수 있다.

x<sup>2</sup><sub>1</sub> + x<sup>2</sup><sub>2</sub> + x<sup>2</sup><sub>3</sub> + . . . + k<sup>2</sup> = n  

이 때 k 는 n 의 제곱근 보다 작은 정수가 될 수 있다.  

그리고 x<sup>2</sup><sub>1</sub> + x<sup>2</sup><sub>2</sub> + x<sup>2</sup><sub>3</sub> + . . . + x<sup>2</sup><sub>i-1</sub> + x<sup>2</sup><sub>i</sub> = n - k<sup>2</sup> 이 되며 이에따라 아래와 같은 식이 성립하게 된다.  

```python
D[n] = min(D[n-k**2] + 1)
```

이 때, 정수 n 이 완전제곱수일 경우 위의 식과는 예외적으로  
1 이 되는 것을 고려해야 한다.


<br>

## Python3

Dynamic Programming (Bottom-Up)

```python
def is_square(num):
    return int(num**(1/2))**2 == num

def get_min_cnt(num):
    d = [0] * num
    for i in range(num):
        d[i] = i+1
        if not is_square(i+1):
            for j in range(1, int(i**(1/2))+1):
                if d[i-j**2] + 1 < d[i]:
                    d[i] = d[i-j**2] + 1
        else:
            d[i] = 1
    return d[num-1]


N = int(input())
print(get_min_cnt(N))
```
