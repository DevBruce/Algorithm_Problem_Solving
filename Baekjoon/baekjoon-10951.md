# 10951 (A+B - 4)

문제 링크: <https://www.acmicpc.net/problem/10951>

<br>

## 접근방법

해당 문제는 테스트 케이스의 갯수가 정해져있지 않다.  
따라서 EOFError (Ctrl + D)가 발생했을 경우 반복문을 빠져나오도록  
예외처리를 하였다.

<br>

## Python3

```python
while True:
    try:
        tmp = input().split()
        A = int(tmp[0])
        B = int(tmp[1])
        print(A + B)
    except EOFError:
        break
```
