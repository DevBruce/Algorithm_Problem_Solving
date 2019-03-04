# 9093 (단어 뒤집기)

문제 링크: <https://www.acmicpc.net/problem/9093>  

<br>

## Python3

```python
def word_rev(str_raw):
    str_splited = str_raw.split()
    result = list()
    for s in str_splited:
        result.append(s[::-1])
    return ' '.join(result)
        
    
T = int(input())
for _ in range(T):
    print(word_rev(input()))
```
