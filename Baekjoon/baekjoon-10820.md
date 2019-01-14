# 10820 (문자열 분석)

문제 링크: <https://www.acmicpc.net/problem/10820>

<br>

## 특이사항

테스트 케이스의 갯수가 명시되어 있지 않으므로  
예외처리 (`EOFError`)를 활용한다.  

<br>

## Python3

```python
def get_cnt(data):
    lower, upper, number, space = 0, 0, 0, 0
    for s in data:
        if s.islower():
            lower += 1
        elif s.isupper():
            upper += 1
        elif s.isdigit():
            number += 1
        elif s.isspace():
            space += 1
    return lower, upper, number, space


while True:
    try:
        print(*get_cnt(input()))
    except EOFError:
        break
```
