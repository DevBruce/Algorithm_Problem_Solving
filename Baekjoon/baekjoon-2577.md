# 2577 (숫자의 개수)

문제 링크: <https://www.acmicpc.net/problem/2577>

<br>

## Python3

```python
def print_num_cnt(num):
    num_all = '0123456789'
    num_cnt = {str(n):0 for n in num_all}
    for n in str(num):
        num_cnt[n] += 1
    for n in num_cnt.values():
        print(n)


A = int(input())
B = int(input())
C = int(input())
ABC = A * B * C
print_num_cnt(ABC)
```
