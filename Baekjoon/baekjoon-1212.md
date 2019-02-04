# 1212 (8진수 2진수)

문제 링크: <https://www.acmicpc.net/problem/1212>

<br>

## 접근방법

입력받은 수를 `int()` 함수를 통해 10진수로 변형한 뒤,  
`bin()` 함수로 2진수로 변형하였다.  
출력되는 이진수 앞에는 `0x` 가 붙은 문자열이므로 `[2:]` 를 통해  
슬라이싱을 하였다.

<br>

## Python3

```python
n = int(input(), base=8)
print(bin(n)[2:])
```
