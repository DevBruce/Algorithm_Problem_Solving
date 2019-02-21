# 10814 (나이순 정렬)

문제 링크: <https://www.acmicpc.net/problem/10814>

<br>

## 특이사항

`sorted()` 를 사용하면
나이는 오름차순으로 정렬하지만  
두번째 요소인 이름도 알파벳 순으로 정렬해버린다.  
즉 가입순 정렬이 되지않는다.  

이 문제를 해결하기 위해 key 로 나이순으로 정렬하도록 지정한다.  
이럴경우 나이순으로 정렬한 뒤, stable 한 정렬을 하게되므로  
가입순을 유지하게 된다.  

<br>

## Python3

```python
N = int(input())
members = list()

for _ in range(N):
    age, name = input().split()
    members.append((int(age), name))
    
for m in sorted(members, key=lambda x:x[0]):
    print(*m)
```
