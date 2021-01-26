# Shallow copy vs Deep copy

## Shallow copy

```python
a = [1, 2, 3, 4, 5]
b = a		# Shallow copy

a[2] = 5

print(a)
print(b)
```

**[예상 실행 결과]**

```
[1, 2, 5, 4, 5]
[1, 2, 5, 4, 5]
```

**[이유]**

* 위 코드에서 `b = a` 는 b가 a list와 같은 주소를 가지는 shallow copy가 일어난다.
* `a[2] = 5` 의 결과 `a` 리스트의 일부 값이 바뀌게 되면 같은 주소를 가지는 `b` 리스트 또한 값이 바뀐것 처럼 보인다.

* 결론적으로는 하나의 리스트 값을 바꾸었지만, 두 변수 `a`,`b` 가 같은 리스트를 가지고 있기 때문에 위와같은 상황이 발생한다.



## Deep copy

### [sol 1] `list(a)`

* 위와같은 상황을 해결하기 위해서는 deep copy 즉, 값 복사가 일어나야한다.

```python
a = [1, 2, 3, 4]

b = list(a) # list를 새로운 list로 형변환
b[0] = 100

print(a)
print(b)

```

##### [output]

```plain
[1, 2, 3, 4]
[100, 2, 3, 4]
```

* 이와같은 방법은 1차원 배열에 한하여 가능한 방법이다.
* 2차원 배열에서 사용할 경우 list 내부의 list에 대해서는 deep copy를 보장해주지 않는다.



### [sol 2] `import copy`

```python
import copy

a = [[1, 2, 3], 2, 3]
b = copy.deepcopy(a)

print(a, b)

b[0][0] = 100
print(a, b)
```

##### [output]

```
[[1, 2, 3], 2, 3] [[1, 2, 3], 2, 3] 		#변경 전
[[1, 2, 3], 2, 3] [[100, 2, 3], 2, 3]		#변경 후
```

* `deepcopy()` 메소드를 활용하여 완벽한 deepcopy를 할 수 있다.



