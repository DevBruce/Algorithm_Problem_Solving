# 11721 (열 개씩 끊어 출력하기)

문제 링크: <https://www.acmicpc.net/problem/11721>

<br>

## Python3

```python
W = input()

tmp = ''
for idx, s in enumerate(W):
    if idx > 0 and idx % 10 == 0:
        tmp += ','
    tmp += s

for splited in tmp.split(','):
    print(splited)
```
