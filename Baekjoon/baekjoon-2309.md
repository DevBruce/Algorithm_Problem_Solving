# 2309 (일곱 난쟁이)

문제 링크: <https://www.acmicpc.net/problem/2309>

<br>

## 접근방법

- 브루트 포스

일곱 난쟁이 키의 합은 100 이어야 하며, 주어지는 난쟁이 키의 갯수는 9개이다.  
즉, 주어진 난쟁이 키의 합에서 2개의 값을 뺀 값이 100 인 경우를 구하여 반환하는 방식으로 접근

<br><br>

## Python3

```python
heights = list()
for _ in range(9):
    heights.append(int(input()))


def get_result(heights):
    heights = heights.copy()
    h_sum = sum(heights)
    for i in range(9):
        for j in range(i+1, 9):
            e1, e2 = heights[i], heights[j]
            if h_sum - (e1 + e2) == 100:
                heights.remove(e1)
                heights.remove(e2)
                heights.sort()
                return heights


result = get_result(heights=heights)
for h in result:
    print(h)
```
