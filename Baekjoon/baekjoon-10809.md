# 10809 (알파벳 찾기)

문제 링크: <https://www.acmicpc.net/problem/10809>

<br>

## Python3

```python
alphabet_all = ['a', 'b', 'c', 'd', 'e', 'f',
           'g', 'h', 'i', 'j', 'k', 'l',
           'm', 'n', 'o', 'p', 'q', 'r',
           's', 't', 'u', 'v', 'w', 'x',
           'y', 'z']

S = input()

for a in alphabet_all:
    print(S.find(a), end=' ')
```
