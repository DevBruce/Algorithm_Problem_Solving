# 1924 (2007년)

문제 링크: <https://www.acmicpc.net/problem/1924>

<br>

## 특이사항

datetime 모듈의 `weekday()` 는  
월요일 0,  
화요일 1  
. . .  
일요일 6 을 반환한다.

<br>

## Python3

```python
import datetime

def get_day(a, b):
    day_list = ['MON', 'TUE', 'WED', 'THU', 'FRI', 'SAT', 'SUN']
    return day_list[datetime.date(2007, a, b).weekday()]


raw = input().split()
x, y = int(raw[0]), int(raw[1])
print(get_day(x, y))
```
