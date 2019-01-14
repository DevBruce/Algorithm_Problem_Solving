# 10828 (스택)

문제 링크: <https://www.acmicpc.net/problem/10828>

<br>

## Python3

Python 의 list 를 상속받아 Stack 을 구현

```python
class Stack(list):
    push = list.append
    
    def size(self):
        return len(self)
        
    def empty(self):
        return 1 if not self.size() else 0
    
    def top(self):
        return self[-1]


stack = Stack()
N = int(input())

for _ in range(N):
    cmd = input()
    if cmd[:3+1] == 'push':
        push_data = int(cmd[5:])
        stack.push(push_data)
    elif cmd == 'pop':
        if stack.size():
            print(stack.pop())
        else:
            print(-1)
    elif cmd == 'size':
        print(stack.size())
    elif cmd == 'empty':
        print(stack.empty())
    elif cmd == 'top':
        if stack.size():
            print(stack.top())
        else:
            print(-1)
```
