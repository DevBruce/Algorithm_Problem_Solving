# 2004 (조합 0의 개수)

문제 링크: <https://www.acmicpc.net/problem/2004>

<br>

## Python3

```python
def two_cnt(num):
    result = 0
    i = 2
    while i <= num:
        result += num // i
        i *= 2
    return result

def five_cnt(num):
    result = 0
    i = 5
    while i <= num:
        result += num // i
        i *= 5
    return result


n, m = map(int, input().split())
n_fac = (two_cnt(n), five_cnt(n))
n_minus_m_fac = (two_cnt(n-m), five_cnt(n-m))
m_fac = (two_cnt(m), five_cnt(m))

result_two_cnt = n_fac[0] - n_minus_m_fac[0] - m_fac[0]
result_five_cnt = n_fac[1] - n_minus_m_fac[1] - m_fac[1]
result = min(result_two_cnt, result_five_cnt)
print(result)
```
