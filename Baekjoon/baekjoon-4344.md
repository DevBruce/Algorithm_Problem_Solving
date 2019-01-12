# 4344 (평균은 넘겠지)

문제 링크: <https://www.acmicpc.net/problem/4344>

<br>

## Python3

```python
def get_over_avg_rate(data):
    raw_to_int_list = [int(s) for s in data]
    N, *score_list = raw_to_int_list
    score_avg = sum(score_list) / N
    
    over_avg_cnt = 0
    for s in score_list:
        if s > score_avg:
            over_avg_cnt += 1
    return (over_avg_cnt / N) * 100


C = int(input())

for _ in range(C):
    raw = input().split()
    result = get_over_avg_rate(raw)
    print(f'{result:0.3f}%')
```
