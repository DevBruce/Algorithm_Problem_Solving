# 11576 (Base Conversion)

문제 링크: <https://www.acmicpc.net/problem/11576>

<br>

## 접근방법

A 진법의 수를 10 진법의 수로 변형한 뒤,  
10 진법의 수를 B 진법으로 변형한다.  

<br>

## Python3

```python
def convert_num(num, base):
    result = ''
    while num != 0:
        num, rmd = divmod(num, base)
        if rmd > 9:
            result += chr(55+rmd)
        else:
            result += str(rmd)
    return result[::-1] if result else '0'

def convert_chr(x):
    x = int(x)
    return chr(55 + x) if x > 9 else str(x)

def convert_ord(x):
    return str(ord(x)-55) if x.isalpha() else x
        

A, B = map(int, input().split())
m = int(input())
raw_num = map(convert_chr, input().split())
converted_int = int(''.join(raw_num), base=A)
converted_B = convert_num(converted_int, B)
result = map(convert_ord, converted_B)
print(' '.join(result))
```
