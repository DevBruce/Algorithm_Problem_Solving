# 1546 (평균)

문제 링크: <https://www.acmicpc.net/problem/1546>

<br>

## Python3

```python
N = int(input())
scores = list(map(int, input().split()))
max_score = max(scores)
converted_scores = map(lambda x : x / max_score * 100, scores)
print(f'{sum(converted_scores)/N:0.02f}')
```
