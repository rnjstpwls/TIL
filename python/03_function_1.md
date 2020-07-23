### 03_function_Ⅰ(수정)

___



#### 함수(function)

함수란 특정한 기능을 하는 코드의 묶음이다.



* 함수를 왜 써야할까?

  

Startcamp때 사용했던 random을 떠올려보자 ..

random.choice를 사용하여 점심메뉴 추천을 받았고, random.sample을 통해 로또번호를 추첨받았다.



우리가 random함수를 직접 구현하기는 어렵다.

>  python random sample github를 구글에 검색하면 원래 코드를 볼 수 있다.
>
> 실제로 엄청 복잡하다.

그러나 우리는 random을 편하게 사용할 수 있다.



바로 함수 덕분이다.



####  _함수를 사용하면 반복되는 코드를 줄일 수 있다._



* 함수의 선언과 호출

```python
def func(x):
    ...
    return f(x)
```



* 함수의 입력(Input)

  1. 매개변수(parameter)

     함수의 정의 부분에서 사용된다.

  2. 전달인자(argument)

     함수를 호출하는 부분에서 사용된다.

```python
def func(x):
    ..
    
func(2)
```

​			즉, 위의 예시 코드에서 x가 매개변수에 해당되고 2가 전달인자에 해당된다.



* 함수의 위치



* 기본 인자 값(Default Argument Values)

  기본인자값을 쓰면 함수를 더 유연하게 사용할 수 있다.

  기본인자값이란 값이 들어오지 않아도 기본 값을 사용하는 것이다.

```python
def greeting(name='익명'):
    return f'{name}, 안녕?'
```



함수를 호출할 때 인자가 없으면 기본 인자 값이 활용된다.



#### _※주의: 단, 기본 인자 값을 가지는 인자 다음에 기본 값이 없는 인자를 사용할 수는 없다._

```python
def greeting(name='익명', grade):
    return f'{grade}학년 {name}님, 환영합니다.'
```

다음과 같이 작성하게되면 SyntaxError가 발생한다.

왜냐하면

```python
greeting(4)
```

을 입력하였을 경우 4가 name에 해당하는지 grade에 해당하는지 판단할 수 없기 때문이다.



#### _컴퓨터는 확실하지 않으면 오류를 낸다._



즉, 기본인자값을 사용하고 싶을 경우 다 쓰던가 뒤에만 쓰도록 하자



* 키워드 인자(keyword arguments)

  키워드 인자를 활용하면 직접 변수의 이름으로 특정 인자를 전달할 수 있다.

  키워드 순서를 바꿔도 그 값이 들어간다.

```python
def greeting(age, name='익명')

greeting(20, '홍길동')
greeting(age = 20, name = '홍길동')
greeting(name = '홍길동', age = 20)
```

​	모두 활용 가능하다. 하지만 키워드 인자를 활용한 다음에 위치 인자를 활용할 수 없다.

```python
greeting(name = '홍길동', 20)
```

​	위와 같이 코드를 작성하면 SyntaxError가 발생한다.



​	따라서, 키워드 인자를 쓸거면 다 쓰던지 아니면 뒤에만 쓰도록 하자



#### 		_앞에는 썻는데 뒤에 안쓰면 에러가 발생한다_





* 함수의 return

  return은 어떤 값이나 형식으로 반환된다. return 값이 없으면, None을 반환한다.

  어떠한 종류도 상관없지만 오직 한 개의 객체만 반환된다.

  함수가 return되거나 종료되면, 함수를 호출한 곳으로 돌아간다.



​		항상 사용했던 print도 함수이기 때문에 return이 존재한다. print의 return은 None이다.



####		_★★★★ 매우중요_

```python
result = print('hi')
type(result) # NoneType
print(result) # None
```

​		즉, print는 문자열을 return하는 것이 아니라 화면에 출력된 형태를 보여주고 None을 return하는 함수이다.



* 인자 리스트 언패킹
  * 패킹 : 여러 개의 값을 하나의 컬렉션으로 묶어 변수에 대입하는 것
  * 언패킹 : 컬렉션 속의 요소들을 여러 개의 변수에 나누어 대입하는 것

___

[정리]

### 함수

1. 함수를 사용하는 이유

   * 한 번 정의하면 이후에는 재활용 해서 사용할 수 있기 때문
   * 코드의 짜임새가 좋아지며 간결하게 표현할 수 있기 때문

2. 함수의 기본 특징

   * `return` : input을 가공한 결과로 함수 밖에서 활용하기 위해 내보내는 역할.
     * 함수는 그 즉시 종료된다.
   * argument (인자) : 함수에 input으로 들어오는 값
   * parameter (매개변수) : 함수에 들어올 값을 받는 변수.

3. 함수 호출

   * 정의한 함수의 명과 함수에 필요한 input 값을 같이 넣어주는 형태로 호출
   * 내장함수 : `dir(__builtins__)` 

4. 일급객체(first class object)

   * 파이썬은 객체이며 파이썬 함수는 아래 3가지 조건을 만족하기에 1급 객체이다.	

   * 3가지 조건
     1. 변수에 담을 수 있다.
     2. 인자로 전달할 수 있다.
     3. 반환값으로 전달할 수 있다.

   ```python
   def first():
       return 3
   
   def second():
       return first
   
   def third(func):
       return func()
   
   sample = second()
   third(sample)
   ```

5. 위치 인자 : 매개변수가 선언된 순서대로 인자의 값이 전달하는 형태

   ```python
   def func(a, b):
       return a + b
   
   func(3, 5)
   ```

6. 키워드 인자 : 해당 매개변수에 직접 인자를 전달하는 형태

   ```python
   def func(a, b):
       return a + b
   
   func(a=6, b=7)
   # 위치인자와 같이 사용가능
   func(4, b=10) # 사용 가능
   func(a=9, 10) # 사용 불가 (위치인자가 먼저 나오고 나중에 키워드 인자를 사용해야 하기 때문)
   func(8, a=10) # 사용 불가 (위치 인자로 a가 전달이 되었는데 키워드 인자로 다시 전달되기 때문에 에러발생.)
   ```

7. 기본값 인자 : 매개변수에 초기 값을 설정한 형태

   ```python
   def func(a, b=5):
       return a + b
   
   func(3, 4) -> 7
   func(2) -> 7
   ```

8. 가변 인자 리스트

   * 입력되는 인자의 갯수가 정해져 있지 않을때 사용.
   * 가변인자로 들어오는 인자들은 `tuple`형태로 저장되어 진다.
   * 매개변수 앞에 `*`를 붙여주는 형태로 가변인자를 받을 수 있음.

   ```python
   def func(*args):
       print(type(args))	# tuple
       print(args)			# (받은 인자, 인자2, 인자3, ... )
   ```

9. 정의 되지 않은 키워드 인자

   * 입력되는 키워드가 다양할 때 주로 사용.
   * `dictionary`형태로 저장이 되어짐.
   * 매개변수 앞에 `**`를 붙여주는 형태로 정의

   ```python
   def func(**kwargs):
       print(type(kwargs))	# dictionary
       print(kwargs)		# {키워드: 값, 키워드2: 값2, 키워드3, 값3}
   ```

10. 이름공간 (name space)          _부제: 우리집 중2 히키코모리 동생._

    * LEGB

    ```text
    L : Local (정의된 함수 내부)
    E : Enclosed (함수 내부에 다시 함수가 정의 되어 있을때 내부함수가 아닌 바깥의 함수)
    G : Global (함수 밖의 변수)
    B : Built-in (파이썬이 제공하는 변수나 함수)
    ```

11. 재귀함수

    * 함수가 함수 본인을 내부에서 호출하는 형태
    * 작고 반복적인 문제로 나눌 수 있는 문제를 해결하지 위해 사용
    * 재귀함수는 `메모리를 많이 사용하기 때문에 사용에 신중할 필요가 있다.` (공간 복잡도 상승)

    ```python
    def fib(n):
        if n < 2:
            return 1
        else:
            return fib(n-1) + fib(n-2)
    ```

    