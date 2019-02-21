# 11004 (K번째 수)

문제 링크: <https://www.acmicpc.net/problem/11004>

<br>

## Python3

```python
N, K = map(int, input().split())
A = list(map(int, input().split()))

print(sorted(A)[K-1])
```
