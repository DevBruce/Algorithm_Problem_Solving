# 2751 (수 정렬하기 2)

문제 링크: <https://www.acmicpc.net/problem/2748>

<br>

## 특이사항

시간초과 문제를 해결하기 위해  
`input()` 대신 `sys.stdin.readline()` 을 사용하였다.

<br>

## Python3

```python
import sys
sys_input = sys.stdin.readline


N = int(sys_input())
nums = list()
for _ in range(N):
    nums.append(int(sys_input()))

for n in sorted(nums):
    print(n)
```
