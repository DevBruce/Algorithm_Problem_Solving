# 1406 (에디터)

문제 링크: <https://www.acmicpc.net/problem/1406>

<br>

## 접근방법

- 스택

<br>

## 특이사항

Python3 로 제출할 경우 시간 초과가 나타나서  
PyPy3 로 제출하여 문제를 해결하였다.  

<br>

## PyPy3

```python
left = list(input())
right = list()    
N = int(input())

for _ in range(N):
    cmd = input().split()
    if cmd[0] == 'L':
        if left: right.append(left.pop())
    elif cmd[0] == 'D':
        if right: left.append(right.pop())
    elif cmd[0] == 'B':
        if left: left.pop()
    elif cmd[0] == 'P':
        left.append(cmd[1])
        
while left:
    right.append(left.pop())
while right:
    print(right.pop(), sep='', end='')
```
