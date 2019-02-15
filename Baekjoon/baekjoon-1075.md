# 1075 (나누기)

문제 링크: <https://www.acmicpc.net/problem/1075>

<br>

## Python3

```python
N = input()
F = int(input())

N_modified = int(N[:-2] + '00')
for i in range(99):
    if N_modified % F == 0:
        print(str(N_modified)[-2:])
        break
    N_modified += 1
```
