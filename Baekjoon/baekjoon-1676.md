# 1676 (팩토리얼 0의 개수)

문제 링크: <https://www.acmicpc.net/problem/1676>

<br>

## 접근방법

0 의 갯수는 소인수 분해를 하였을 때  
`2 x 5` 가 몇번 나타나는지를 통해 알 수 있다.  

이 때 팩토리얼 계산의 특성상 소인수 분해시  
`2` 는 `5` 보다 자연스럽게 많을 수 밖에 없으므로  
소인수 분해의 결과에서 `5` 의 갯수만을 구하면 답을 쉽게  
구할 수 있다.

<br>

## Python3

```python
def get_zero_cnt(num):
    result = 0
    for i in range(2, num+1):
        while i % 5 == 0:
            result += 1
            i //= 5
    return result


N = int(input())
print(get_zero_cnt(N))
```
