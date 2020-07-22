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