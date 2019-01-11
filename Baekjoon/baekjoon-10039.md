# 10039 (평균 점수)

문제 링크: <https://www.acmicpc.net/problem/10039>

<br>

## Python3

```python
score_sum = 0
for _ in range(5):
    score = int(input())
    if score <= 40:
        score = 40
    score_sum += score

print(score_sum // 5)
```
