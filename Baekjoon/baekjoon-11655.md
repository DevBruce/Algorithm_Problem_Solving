# 11655 (ROT13)

문제 링크: <https://www.acmicpc.net/problem/11655>

<br>

## 특이사항

- `ord()` 함수를 통해 해당 문자의 ASCII 코드를 구할 수 있다.  

- `chr()` 함수를 통해 해당 ASCII 코드에 해당하는 문자를 구할 수 있다.  

- 알파벳의 갯수 : 26

- 알파벳 대문자 ASCII Code : 65(A) ~ 90(Z)

- 알파벳 소문자 ASCII Code : 97(a) ~122(z)

<br>

## Python3

```python
def ch_ROT13(alphabet):
    x = 96 if alphabet.islower() else 64
    encrypted = ord(alphabet) - x + 13
    if encrypted != 26: encrypted %= 26
    return chr(encrypted + x)


S = input()
result = ''
for s in S:
    result += ch_ROT13(s) if s.isalpha() else s

print(result)
```
