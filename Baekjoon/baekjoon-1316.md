# 1316 (그룹 단어 체커)

문제 링크: <https://www.acmicpc.net/problem/1316>

<br>

## Python3

```python
def check_group_word(data):
    alp_bag = list()
    for alp in data:
        if alp not in alp_bag:
            alp_bag.append(alp)
        else:
            if alp_bag[-1] == alp:
                pass
            else:
                return 0
    return 1


N = int(input())
result = 0
for _ in range(N):
    result += check_group_word(input())
    
print(result)
```
