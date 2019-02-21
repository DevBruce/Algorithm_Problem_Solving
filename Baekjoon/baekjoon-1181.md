# 1181 (단어 정렬)

문제 링크: <https://www.acmicpc.net/problem/1181>

<br>

## 접근방법

1순위가 단어의 길이,  
2순위가 사전순 이므로  

`(단어의 길이, 단어)` 의 형태를 가지는 튜플로 묶어서  
리스트에 추가한다.  

이 후 `sorted()` 함수를 통해 정렬한다.  

<br>

## Python3

```python
N = int(input())
words = list()

for _ in range(N):
    word = input()
    length = len(word)
    word_set = length, word
    if not word_set in words:
        words.append(word_set)

for w in sorted(words):
    print(w[1])
```
