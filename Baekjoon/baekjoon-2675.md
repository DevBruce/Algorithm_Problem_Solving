# 2675 (문자열 반복)

문제 링크: <https://www.acmicpc.net/problem/2675>

<br>

## Python3

```python
def re_S(raw):
    data = raw.split()
    R, S = int(data[0]), data[1]   
    result = ''
    for s in S:
        result += s * R
    print(result)


T = int(input())
for _ in range(T):
    re_S(input())
```
