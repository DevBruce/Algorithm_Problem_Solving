# 10808 (알파벳 갯수)

문제 링크: <https://www.acmicpc.net/problem/10808>

<br>

## Python3

```python
alphabet_all = ['a', 'b', 'c', 'd', 'e', 'f',
           'g', 'h', 'i', 'j', 'k', 'l',
           'm', 'n', 'o', 'p', 'q', 'r',
           's', 't', 'u', 'v', 'w', 'x',
           'y', 'z']

def get_cnt(data):
    alp_cnt_dict = dict()
    for a in alphabet_all:
        alp_cnt_dict[a] = 0
        
    for s in data:
        alp_cnt_dict[s] += 1
    return alp_cnt_dict.values()


print(*get_cnt(input()))
```
