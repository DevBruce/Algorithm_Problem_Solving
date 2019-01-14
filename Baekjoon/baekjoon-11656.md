# 11656 (접미사 배열)

문제 링크: <https://www.acmicpc.net/problem/11656>

<br>

## Python3

```python
def sorted_suffix(data):    
    suffix_list = list()
    for i in range(len(S)):
        suffix_list.append(S[i:])
    return sorted(suffix_list)


S = input()
for s in sorted_suffix(S):
    print(s)
```
