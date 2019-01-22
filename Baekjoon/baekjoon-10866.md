# 10866 (덱)

문제 링크: <https://www.acmicpc.net/problem/10866>

<br>

## Python3

```python
class Node:
    def __init__(self, data):
        self.data = data
        self.left = None
        self.right = None
        

class Deque:
    def __init__(self):
        self.front = None
        self.back = None
        self.size = 0
        
    def push_front(self, data):
        new = Node(data)
        if not self.is_empty():
            new.right = self.front
            self.front.left = new
            self.front = new
        else:
            self.front = new
            self.back = new
        self.size += 1
    
    def push_back(self, data):
        new = Node(data)
        if not self.is_empty():
            new.left = self.back
            self.back.right = new
            self.back = new
        else:
            self.back = new
            self.front = new
        self.size += 1
    
    def pop_front(self):
        if not self.is_empty():
            tmp = self.front.data
            self.front = self.front.right
            if self.front: self.front.left = None
            self.size -= 1
            return tmp
        else:
            print('Empty Deque')
    
    def pop_back(self):
        if not self.is_empty():
            tmp = self.back.data
            self.back = self.back.left
            if self.back: self.back.right = None
            self.size -= 1
            return tmp
        else:
            print('Empty Deque')
    
    def get_front(self):
        if not self.is_empty():
            return self.front.data
        else:
            print('Empty Deque')
    
    def get_back(self):
        if not self.is_empty():
            return self.back.data
        else:
            print('Empty Deque')
    
    def get_size(self):
        return self.size
    
    def is_empty(self):
        return 0 if self.get_size() else 1

    
deque = Deque()
N = int(input())

for _ in range(N):
    cmd = input()
    if cmd.split()[0] == 'push_front':
        deque.push_front(int(cmd.split()[1]))
    elif cmd.split()[0] == 'push_back':
        deque.push_back(int(cmd.split()[1]))
    elif cmd == 'pop_front':
        if not deque.is_empty():
            print(deque.pop_front())
        else:
            print(-1)
    elif cmd == 'pop_back':
        if not deque.is_empty():
            print(deque.pop_back())
        else:
            print(-1)
    elif cmd == 'front':
        if not deque.is_empty():
            print(deque.get_front())
        else:
            print(-1)
    elif cmd == 'back':
        if not deque.is_empty():
            print(deque.get_back())
        else:
            print(-1)
    elif cmd == 'empty':
        print(deque.is_empty())
    elif cmd == 'size':
        print(deque.get_size())
```
