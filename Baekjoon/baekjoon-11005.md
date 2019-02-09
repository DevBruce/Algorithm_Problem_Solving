# 11005 (진법 변환 2)

문제 링크: <https://www.acmicpc.net/problem/11005>

<br>

## 특이사항

- `divmod(x, y)` 는 튜플 `(x//y, x%y)` 반환  

- 나머지가 9 를 넘어갈 경우 알파벳 대문자 A 부터 시작된다.  
알파벳은 ASCII 를 활용하여 처리하였다.

> A ~ Z : ASCII 65 ~ 90

<br>

## Python3

```python
def convert_base(num, base):
    result = ''
    while num != 0:
        num, rmd = divmod(num, base)
        if rmd > 9:
            result += chr(55+rmd)
        else:
            result += str(rmd)
    return result[::-1] or '0'


N, B = map(int, input().split())
print(convert_base(N, B))
```
