# 2004 (조합 0의 개수)

문제 링크: <https://www.acmicpc.net/problem/2004>

<br>

## 접근방법

`nCm` 은 `n!` / `(n-m)! m!` 과 동일하다.  

따라서 `n!` 에서의 0 의 갯수에서  

`(n-m)!` 의 0 의 갯수를 빼고  
`m!` 의 0 의 갯수를 빼주는 방식으로 `nCm` 의 0 의 갯수를 구할 수 있다.  

팩토리얼 값에서 0 의 갯수를 구하는 방법은  
해당 값을 소인수 분해를 했을 때 인수 5 의 갯수를 구하면 된다.  
(팩토리얼 연산을 통해 나온 값을 소인수 분해했을 때 인수 2 의 갯수가 인수 5 보다 무조건 많을 수 밖에 없기 때문이다.)  

하지만 이번 경우에서는 소인수 분해를 했을 때  
**인수 2 와 인수 5 의 갯수 중 작은 값이 된다.**  
단순한 팩토리얼 연산이 아닌, 팩토리얼 연산 후 다른 팩토리얼 연산값으로 나누는 과정이  
있기 때문에 인수 2 의 갯수가 인수 5 의 갯수보다 작은 경우가 발생할 수 있기 때문이다.  

<br>

팩토리얼 연산한 값에서 소인수 분해를 했을 때  
인수 2 의 갯수를 구하는 방법은 다음과 같다.  

`n!` 이 있을 때 아래의 항목들을 모두 더한다.  

- n 을 2 로 나눈 몫

- n 을 2<sup>2</sup> 으로 나눈 몫

- n 을 2<sup>3</sup> 으로 나눈 몫

- . . .

- n 을 2<sup>n</sup> 으로 나눈 몫 (2<sup>n</sup> <= n!)

<br>

이 과정을 아래의 예시로 설명하겠다.

만약 `12!` 이 있다면 해당 값은 아래와 같다.  

```
12! = 1 x 2 x 3 x 4 x 5 x 6 x 7 x 8 x 9 x 10 x 11 x 12
```

이 때 2의 배수에 해당하는 6개의 수(2, 4, 6, 8, 10, 12)는 당연하게도  
각각 2 를 인수로 가지는 값들이다.  
이러한 수들의 갯수를 구하는 방법은 12 를 2 로 나눈 몫이 된다.  

그런데, 6개의 수 중에서 인수 2 를 두번 이상 인수로 가지는 수들이 존재한다.  

4 는 인수 2 를 두번,  
8 은 인수 2 를 세번,  
12 인수 2를 두번 가진다.  

즉, 4 의 배수는 2<sup>2</sup> 을 인수로 가지므로 2 를 인수로 두번 가진다.  
즉 추가적인 카운트가 필요하다.  
따라서 12 나누기 2<sup>2</sup> 의 몫 3이 추가해야할 카운트 값이다.  

8 의 배수는 2<sup>3</sup> 을 인수로 가지므로 2 를 인수로 세번 가진다.  
이 또한 마찬가지로 추가적인 카운트가 필요하다.  
따라서 12 나누기 2<sup>3</sup> 의 몫 1이 추가해야할 카운트 값이된다.  

2<sup>4</sup> 인 16 은 12 를 넘어가는 수이므로 위의 과정을 중단한다.  

따라서 `12!` 는 2 를 인수로 10번(= 6 + 3 + 1) 가지는 것을 구할 수 있다.  

5 의 인수 갯수를 구하는 방법도 위와 동일하다.

<br><br>

## Python3

```python
def two_cnt(num):
    result = 0
    i = 2
    while i <= num:
        result += num // i
        i *= 2
    return result

def five_cnt(num):
    result = 0
    i = 5
    while i <= num:
        result += num // i
        i *= 5
    return result


n, m = map(int, input().split())
n_fac = (two_cnt(n), five_cnt(n))
n_minus_m_fac = (two_cnt(n-m), five_cnt(n-m))
m_fac = (two_cnt(m), five_cnt(m))

result_two_cnt = n_fac[0] - n_minus_m_fac[0] - m_fac[0]
result_five_cnt = n_fac[1] - n_minus_m_fac[1] - m_fac[1]
result = min(result_two_cnt, result_five_cnt)
print(result)
```