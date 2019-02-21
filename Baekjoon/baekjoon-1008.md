# 1008 (A/B)

문제 링크: <https://www.acmicpc.net/problem/1008>

<br>

## 특이사항

"절대/상대 오차는 10<sup>-9</sup> 까지 허용" 조건에 의해  
소수점 9자리까지만 출력해야한다.

<br>

## Python3

```python
A, B = map(int, input().split())
print(f'{A/B:0.9f}')
```
