# 15552 (빠른 A+B)

문제 링크: <https://www.acmicpc.net/problem/15552>

<br>

## 특이사항

`input()` 대신 `sys.stdin.readline` 를 사용하여  
시간초과 문제를 해결할 수 있다.

`sys.stdin.readline` 의 경우 입력받은 값 뒤에  
`\n` 이 추가되는 특징이 있다.

<br>

## Python3

```python
import sys
sys_input = sys.stdin.readline

T = int(sys_input())

for _ in range(T):
    raw = sys_input().split()
    A, B = int(raw[0]), int(raw[1])
    print(A + B)
```
