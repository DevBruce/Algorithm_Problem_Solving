# 9012 (괄호)

문제 링크: <https://www.acmicpc.net/problem/9012>  

- 스택

<br>

## Python3

```python
def check_ps(parenthesis):
    stack = 0
    for p in parenthesis:
        if p == '(':
            stack += 1
        else:  # p == ')'
            if stack == 0:
                print('NO')
                break
            else:
                stack -= 1
    else:
        print('NO') if stack else print('YES')

        
T = int(input())

for _ in range(T):
    check_ps(input())
```
