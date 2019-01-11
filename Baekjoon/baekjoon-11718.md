# 11718 (그대로 출력하기)

문제 링크: <https://www.acmicpc.net/problem/11718>

<br>

## Python3

```python
while True:
    try:
        print(input())
    except EOFError:
        break
```
