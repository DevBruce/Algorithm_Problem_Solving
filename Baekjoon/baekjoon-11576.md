# 11576 (Base Conversion)

문제 링크: <https://www.acmicpc.net/problem/11576>

<br>

## 접근방법

A 진법의 수를 10 진법의 수로 변형한 뒤,  
10 진법의 수를 B 진법으로 변형한다.  

<br>

## Python3

```python
def convert_decimal(num_list, base):
    num_reversed = num_list[::-1]
    result = 0
    for idx, n in enumerate(num_reversed):
        result += (base ** idx) * n
    return result

def convert_base(num, base):
    result = list()
    while num != 0:
        num, rmd = divmod(num, base)
        result.append(rmd)
    return result[::-1] or [0]
        

A, B = map(int, input().split())
m = int(input())
raw_num = list(map(int, input().split()))

converted_decimal = convert_decimal(raw_num, base=A)
converted_B = convert_base(converted_decimal, base=B)
print(*converted_B)
```
