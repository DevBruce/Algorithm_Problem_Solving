# 10799 (쇠막대기)

문제 링크: <https://www.acmicpc.net/problem/10799>

<br>

## 접근방법

- 스택

전달받은 괄호 문자열을 반복문을 통해 순회한다.  
이 때 `(` 일 경우에는 해당 괄호의 인덱스를 스택에 push 한다.  

`)` 일 경우 일단 스택의 top 에 해당하는 `(` 의 인덱스를 pop 하여 임의의 변수에 저장한다.  
이후 두가지 경우로 나뉜다.

<br>

**i )** pop하여 가져온 `(` 의 인덱스와 현재 `)` 의 인덱스의 차가 1인 경우  

이 경우는 `()` 형태가 되어 레이저가 된다.  
따라서 스택에 쌓여있는 `(` 의 갯수 (실제로는 `(` 의 인덱스값이 쌓여있다.) 만큼 쇠막대기 갯수가 추가된다.  

<br>

**ii )** pop하여 가져온 `(` 의 인덱스와 현재 `)` 의 인덱스의 차가 1이 아닌 경우  

이 경우에는 왼쪽에 위치한 레이저 `()` 에 의해서 쇠막대기 갯수가 1개 추가되는 형태가 된다.  

<br>

## Python3

```python
def get_cnt(iron_bars):
    cnt = 0
    stack = list()
    for idx, p in enumerate(iron_bars):
        if p == '(':
            stack.append(idx)
        else:
            idx_popped = stack.pop()
            if idx - idx_popped == 1:
                cnt += len(stack)
            else:
                cnt += 1
    return cnt


ps = input()
print(get_cnt(ps))
```
