# 문자열(String)
* 변경할 수 없고(immutable) 
* 순서가 있고(ordered)
* 순회 가능한(iterable)

## 문자열의 다양한 조작법(method)

### 1. 조회/탐색 
### `.find(x)`
> x의 첫번째 위치를 반환, 없으면 `-1`을 반환
```python
a = 'apple'
a.find('a') #return 0
a.find('pp') #return 1
a.find('k') #return -1
```

### `.index(x)`
> x의 첫번째 위치를 반환, 없으면 오류를 발생시킴
```python
a = 'apple'
a.index('k') #오류 발생
``` 

### 2. 값 변경
### `replace(old, new[, count])`
> 바꿀 대상 글자를 새로운 글자로 바꿔서 반환, count를 지정하면 해당 갯수만큼 시행
```python
a = 'apple'
a.replace('p', '') # return 'aple'

a = 'pine apple'
a.replace('p', 'k', 3) # return 'kine akkle'
# p 3개가 k로 바뀌었다.
```

### `strip([chars])`
> 특정한 문자들을 지정하면, 양쪽을 제거하거나 왼쪽을 제거하거나(`lstrip`) , 오른쪽을 제거 (`rstrip`).

* 지정하지 않으면 공백을 제거함
* `\n` , `\t`, `\r` 모두 공백으로 구분
* `strip()` 대상이 문자열의 맨앞, 맨뒤가 아니면 아무일도 일어나지 않음
```python
oh = '     oh!\n\t\r'
oh.strip() #return 'oh!'

a = 'apple'
a.strip('a') #return 'pple' => 'a'가 지워짐
a.strip('l') #return 'apple' => 아무것도 지워지지 않음
```

### `split()`
> 문자열을 특정한 단위로 나누어 리스트로 반환

* 단위를 설정하지 않으면 공백을 기준으로 나눔
* 
```python
csv = '1,홍길동,01012341234'
csv.split(',') # return ['1','홍길동','01012341234']

a = 'a b c'
a.split() # return ['a', 'b', 'c']
```
### `'separator'.join(iterable)`
> 특정한 문자열로 만들어 반환

> 반복 가능한(iterable) 컨테이너의 요소들을 separator를 구분자로 합쳐 (`join()`) 문자열로 반환합니다.

```python
word = '배고파'
words = ['안녕', 'hello']

'!'.join(word) # return '배!고!파'
'!'.join(words) # return '안녕!hello'
```
### 3. 문자 변경
### `.capitalize()`, `title()`, `upper()`, `.lower()`, `.swapcase()`

> `.capitalize()` : 앞글자를 대문자로 만들어 반환

> `.title()` : 어포스트로피나 공백 이후를 대문자로 만들어 반환

> `.upper()` : 모두 대문자로 만들어 반환

> `.lower()` : 모두 소문자로 만들어 반환

> `.swapcase()` : 대<->소문자로 변경하여 반환

```python
a = 'hi! everyone, i\'m kim'
a.capitalize() # return 'Hi! everyone, i'm kim'
a.title() #return 'Hi! Everyone, I'M Kim'
a.upper() #return 'HI! EVERYONE, I'M KIM'
```

### 기타 문자열 관련 검증 메소드 : 참/거짓 반환
> `.isalpha()`, `.isdecimal()`, `.isdigit()`, `.isnumeric()`, `.isspace()`, `.isupper()`, `.istitle()`, `.islower()`

