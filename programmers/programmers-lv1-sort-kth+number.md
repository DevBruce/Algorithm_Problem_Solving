# K번째수

문제 링크: <https://programmers.co.kr/learn/courses/30/lessons/42748>  

- Level 1

- 정렬

<br>

## Python3

```python
def solution(array, commands):
    answer = []
    for cmd in commands:
        i = cmd[0] - 1
        j = cmd[1]
        k = cmd[2] - 1
        array_sliced_sorted = sorted(array[i:j])
        answer.append(array_sliced_sorted[k])
    return answer
```
