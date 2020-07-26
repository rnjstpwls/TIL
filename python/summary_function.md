# 함수

* 함수의 선언

```python
def <함수이름>(parameter1, parameter2):
    <코드 블럭>
    return value
```



- 내장함수 목록

  ```python
  dir(__builtins__)
  ```

* 매개변수(parameter)

  함수를 정의할때 사용

* 전달인자(argument)

  값을 전달할때 사용



*  위치 인자

```python
def func(a, b):
    return a + b

func(3, 5)
```



* 기본 인자 값

인자를 입력하지 않으면 기본 인자 값 반환

```python
def func(a, b=5):
    return a + b

func(3, 4) -> 7
func(3) -> 8
```





- 키워드 인자

```python
func(a=3, b=5)# 가능
func(4, b=5) # 가능
func(a=4, 5) # 불가능
func(5, a=10) # 불가능
```



* 가변 인자

개수가 정해지지 않은 인자를 받을 때 `*args`를 활용한다. args는 `tuple` 이다.

```python
def func(*args):
    print(type(args)) # tuple
    print(args) # (인자1, 인자2, 인자3)
```



* 가변 키워드 인자

`**kwargs` 정해지지 않은 키워드 인자들은 `dict` 형태로 처리 된다.

```python
def func(**kwargs):
    print(type(kwargs)) # dictionary
    print(kwargs) # {key1: value1, key2: value2, key3: value3}
```



- 이름 공간 LEGB

```python
L : local (정의된 함수 내부)
E : Enclosed (함수 내부에 다시 함수가 정의 되어 있을 때 내부함수가 아닌 바깥의 함수)
G : Global(함수 밖의 변수)
B : Built-in(파이썬이 제공하는 변수나 함수)
```



* 변수의 수명주기
  * 빌트인 스코프 : 파이썬이 실행된 이후부터 영원히 유지
  * 전역 스코프 : 모듈이 호출된 시점 이후 혹은 이름이 선언된 이후부터 인터프리터가 끝날때 까지 유지
  * 지역(함수) 스코프 : 함수가 호출될 때 생성되고, 함수가 종료될 때까지 유지