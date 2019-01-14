# 10845 (큐)

문제 링크: <https://www.acmicpc.net/problem/10845>

<br>

## Python3

Python 의 list 를 상속받아 Queue 구현

```python
class Queue(list):
    enqueue = list.append
    
    def dequeue(self):
        return self.pop(0)
    
    def size(self):
        return len(self)
        
    def empty(self):
        return 1 if not self.size() else 0
    
    def back(self):
        return self[-1]
    
    def front(self):
        return self[0]


queue = Queue()
N = int(input())

for _ in range(N):
    cmd = input()
    if cmd[:3+1] == 'push':
        enqueue_data = int(cmd[5:])
        queue.enqueue(enqueue_data)
    elif cmd == 'pop':
        if queue.size():
            print(queue.dequeue())
        else:
            print(-1)
    elif cmd == 'size':
        print(queue.size())
    elif cmd == 'empty':
        print(queue.empty())
    elif cmd == 'front':
        if queue.size():
            print(queue.front())
        else:
            print(-1)
    elif cmd == 'back':
        if queue.size():
            print(queue.back())
        else:
            print(-1)
```
