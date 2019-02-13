# 2960 (에라토스테네스의 체)

문제 링크: <https://www.acmicpc.net/problem/2960>

<br>

## 접근방법

- 에라토스테네스의 체

<br>

## Python3

```python
def get_solution(n, k):
    e = [True for _ in range(n)]
    e[0] = False
    removed_nums = list()
    for i in range(2, n+1):
        if e[i-1]:
            removed_nums.append(i)
            for j in range(i*2, n+1, i):
                e[j-1] = False
                if not j in removed_nums:
                    removed_nums.append(j)
    return removed_nums[k-1]


N, K = map(int, input().split())
print(get_solution(N, K))
```
