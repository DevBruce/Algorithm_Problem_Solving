# 11650 (좌표 정렬하기)

문제 링크: <https://www.acmicpc.net/problem/11650>

<br>

## Python3

```python
N = int(input())
cor_list = list()

for _ in range(N):
    cor = list(map(int, input().split()))
    cor_list.append(cor)

for c in sorted(cor_list):
    print(*c)
```
