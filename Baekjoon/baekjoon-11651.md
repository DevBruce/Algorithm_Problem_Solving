# 11651 (좌표 정렬하기 2)

문제 링크: <https://www.acmicpc.net/problem/11651>

<br>

## Python3

```python
N = int(input())
cor_list = list()

for _ in range(N):
    x, y = map(int, input().split())
    cor_list.append((y, x))
    
for y, x in sorted(cor_list):
    print(x, y)
```
