# 11720 (숫자의 합)

문제 링크: <https://www.acmicpc.net/problem/11720>

<br>

## Python3

### \# 1

```python
N = int(input())
number = input()

result = 0
for n in number:
    result += int(n)

print(result)
```

### \# 2

```python
N = int(input())
number_to_list = [int(n) for n in input()]
print(sum(number_to_list))
```
