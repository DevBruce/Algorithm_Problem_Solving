# 11005 (진법 변환 2)

문제 링크: <https://www.acmicpc.net/problem/11005>

<br>

## 접근 방법

10진법의 수 n 을 k 진법의 수로 변경하기 위해서는  
n 을 k 로 나누고 그 때의 나머지를 임의의 변수에 하나의 요소로 저장한다.  

n 을 k 로 나누었을 때의 몫이 0 이 될 때까지 해당 작업을 반복한 뒤  
저장되어있던 나머지를 역순으로 출력하면 k 진법으로 변환된 수가 출력된다.  

<br>

## 특이사항

`divmod(x, y)` 는  
튜플 `(x//y, x%y)` 를 반환한다.  

나머지가 9 를 넘어갈 경우 알파벳 대문자 A 부터 시작된다.  
알파벳은 ASCII 를 활용하여 처리하였다.

> A ~ Z : ASCII 65 ~ 90

<br>

## Python3

```python
def convert_num(num, base):
    result = ''
    while num > 0:
        num, rmd = divmod(num, base)
        if rmd > 9:
            result += chr(55+rmd)
        else:
            result += str(rmd)
    return result[::-1]


N, B = map(int, input().split())
print(convert_num(N, B))
```
