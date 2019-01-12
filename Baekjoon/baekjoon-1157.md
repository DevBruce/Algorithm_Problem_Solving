# 1157 (단어 공부)

문제 링크: <https://www.acmicpc.net/problem/1157>

<br>

## Python3

```python
word = input().upper()

alp_cnt = dict()
for a in word:
    if a not in alp_cnt.keys():
        alp_cnt[a] = 0
    alp_cnt[a] += 1

if len(alp_cnt) >= 2:
    alp_cnt_sorted = sorted(alp_cnt.values(), reverse=True)  # 최댓값과 중복여부를 비교하기 위해 정렬된 리스트를 구한다.
    if alp_cnt_sorted[0] == alp_cnt_sorted[1]:  # 최댓값이 중복되는지 비교
        print('?')
    else:
        print(max(alp_cnt, key=lambda x : alp_cnt[x]))
else:  # 입력된 단어의 길이가 1인 경우
    print(word)
```
