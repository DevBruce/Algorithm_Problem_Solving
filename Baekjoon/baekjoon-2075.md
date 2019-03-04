# 2075 (N번째 큰 수)

문제 링크: <https://www.acmicpc.net/problem/2075>

<br>

## 접근방법

모든 데이터를 리스트에 담아서 정렬할 경우  
메모리 초과가 발생하므로  
한 줄을 입력받을 때 마다 정렬하는 방식을 사용하였다.

<br>

## Python3

```python
N = int(input())
tmp = list()
for _ in range(N):
    tmp.extend(map(int, input().split()))
    tmp = sorted(tmp, reverse=True)[:N]

print(tmp[N-1])
```
