### 00_Python_Intro

___

> PEP-8 : Python Style Guide (파이썬 공식 스타일 가이드)
>
> 공식 Documentation과 친해질 필요가 있다.
>
> 한번씩 읽어보면서 Coding을 하도록 하자.



#### 주석(comment)

```python
# 한줄주석처리
```

```python
'''
여러줄 주석처리
'''
```



'1줄에 1문장'이 원칙이다.

> 그러나 [] {} ()는 \없이 여러줄에 걸쳐서 작성할 수 있다.

문장은 파이썬이 실행 가능한 최소한의 코드 단위이다.

기본적으로 파이썬에서는 ; 을 작성하지 않는다.



#### 변수

* 할당 연산자(Assignment Operator)

해당 데이터 타입을 확인하기 위해서는 type()을 활용한다.

```python
type(a)
```

해당 값의 메모리 주소를 확인하기 위해서는 id()를 활용한다.

```python
id(a)
```



변수의 개수가 적으면 ValueError가 발생한다.

> a, b = 1, 2, 3

변수의 개수가 많으면 ValueError, TypeError 2가지가 발생한다.

> a, b = 1





* 식별자(Identifiers)

> 식별자의 이름은 영문알파벳, 밑줄(_), 숫자로 구성된다.
>
> 첫 글자에 숫자가 올 수 없다.
>
> 길이에 제한이 없다.
>
> 대소문자를 구별한다.
>
> 미리 지정해둔 예약어는 사용할 수 없다.
>
> ```python
> import keyword
> print(keyword.kwlist)
> ```
>
> 내장함수나 모듈 등의 이름으로도 만들면 안된다.



#### 데이터 타입(Date Type)

* 숫자 타입(Number)

  * int(정수, integer)

    ​	8진수: 0o		2진수: 0b		16진수: 0x

    

    

  * float(부동소수점, 실수, floating point number)

  

  ★중요 : float(부동소수점)을 표현하는 과정에서 항상 같은 값으로 일치되지 않는다. (floating point rounding error)

  >처리방법
  >
  >1. 소수점 10번째 자리 비교
  >
  >   ```python
  >   abs(3.5 - 3.12) <= 10E-10
  >   ```
  >
  >   
  >
  >2.  sys 모듈을 통해 처리
  >
  >   ```python
  >   import sys
  >   abs(a - b) <= sys.float_info.epsilon
  >   ```
  >
  >   
  >
  >3. math 모듈을 통해 처리
  >
  >   ```python
  >   import math
  >   math.isclose(a, b)
  >   ```

  ​		

  컴퓨터식 지수 표현 방식

  

  e를 사용할 수도 있다. (e와 E 둘 중 어느 것을 사용해도 무방)

  ```python
  314e-2
  ```

  * complex (복소수, complex number)

  ```python
  a = 3 + 4j
  ```

  



* 문자 타입(String)

  ★ String interpolation


```python
#%-formatting
print('내 이름은 %s 입니다.' % name)

#str.format()
print('내 이름은 {} 입니다.'.format(name))

#f-strings
print(f'내 이름은 {name} 입니다.')
```



​	이스케이프 시퀀스

```python
\n			줄 바꿈
\t			탭
\r			캐리지리턴
\0			널(Null)
\\			\
\'			'
\"			"
```





* 참/거짓(Boolean)

  True / False

```python
# False
0, 0.0, (), [], {}, '', None 
```



* None 타입



#### 형변환(Type conversion)

* 암시적 형변환
* 명시적 형변환





#### 연산자(Operator)

* 산술 연산자

```python
+		덧셈
-		뺄셈
*		곱셈
/		나눗셈
//		몫
%		나머지(modulo)
**		거듭제곱
```

> #divmod
>
> a, b = divmod(5, 2)



* 비교 연산자

  

* __★논리 연산자__



[AND]

| A     | B     | AND   |
| ----- | ----- | ----- |
| True  | True  | True  |
| True  | False | False |
| False | True  | False |
| False | False | False |



[OR]

| A     | B     | AND   |
| ----- | ----- | ----- |
| True  | True  | True  |
| True  | False | True  |
| False | True  | True  |
| False | False | False |



> __단축평가__
>
> 'a' and 'b'
>
> and는 'a'가 False이면 무조건 False를 출력하고 'a'가 True 이면 'b'를 출력한다.
>
> 
>
>
> 'a' or 'b'
>
> or는 'a'가 True이면 무조건 True를 출력하고 'a'가 False 이면 'b'를 출력한다.





* 복합 연산자





#### 표현식

하나의 값(value)으로 환원될 수 있는 문장



#### 문장

파이썬이 실행 가능한 최소한의 코드 단위