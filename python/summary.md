### 월말평가를 위한 요점정리

___

* 할당연산자

type() 데이터타입

id() 메모리주소



동시에 여러개의 변수에 할당

```python
a = 20, 30 # a가 tuple (20, 30)으로 저장
a, b = 20, 30 # a=20, b=30으로 저장
a, b = 20, 30, 40 # Error
a, b, c = 20, 30 # Error
```



* 식별자

```python
import keyword
print(keyword,kwlist)
```



* 데이터타입(Date Type)

(1) 숫자타입

1. int

   n진수 표현

   0b, 0o, 0x

2. float

   지수 표현방식 (e와 E 둘 중 어느 것을 사용해도 무방)

   지수 표현방식을 쓰면 Date Type은 float형이라고 생각하면됨

   

   실수의 연산 처리하는법

   ```python
   print((a-b)<=1e-10)
   
   import sys
   abs(a - b) <= sys.float_info.epsilon
   
   import math
   print(math.isclose(a,b))
   ```

   

   

3. complex



(2) 문자타입

```python
'hello' * 3
'my name is ' + 'sejin'
```



### 이스케이프 시퀀스

문자열을 활용하는 경우 특수문자 혹은 조작을 하기 위하여 사용되는 것으로 `\`를 활용하여 이를 구분합니다. 

| <center>예약문자</center> |    내용(의미)     |
| :-----------------------: | :---------------: |
|            \n             |      줄 바꿈      |
|            \t             |        탭         |
|            \r             |    캐리지리턴     |
|            \0             |     널(Null)      |
|           \\\\            |        `\`        |
|            \\'            | 단일인용부호(`'`) |
|            \\"            | 이중인용부호(`"`) |



f-string

`f'{name} 안녕'`



(3) Boolean 타입

```python
0, 0.0, (), [], {}, '', None
```

얘들은 False 나머지 True



* 형변환
  * 암시적 형변환
  * 명시적 형변환





* 연산자

  * 산술연산자

  * 비교연산자

    

    | 연산자   | 내용                   |
    | -------- | ---------------------- |
    | `<`      | 미만                   |
    | `<=`     | 이하                   |
    | `>`      | 초과                   |
    | `>=`     | 이상                   |
    | `==`     | 같음                   |
    | `!=`     | 같지않음               |
    | `is`     | 객체 아이덴티티        |
    | `is not` | 부정된 객체 아이덴티티 |

    

  * 논리연산자

    * 단축평가

  * 복합연산자



* 표현식 & 문장

  * 표현식 => evaluate => 값

    하나의 값으로 환원될 수 있는 문장

  * 문장

    파이썬이 실행 가능한 최소한의 코드 단위



___

___

Data Container



Sequence container

=> list, tuple, range, string



* list

[], list()



## 시퀀스에서 활용할 수 있는 연산자/함수 

| operation    | 설명                    |
| ------------ | ----------------------- |
| x `in` s     | containment test        |
| x `not in` s | containment test        |
| s1 `+` s2    | concatenation           |
| s `*` n      | n번만큼 반복하여 더하기 |
| s[i]         | indexing                |
| `s[i:j]`     | slicing                 |
| `s[i:j:k`]   | k간격으로 slicing       |
| len(s)       | 길이                    |
| min(s)       | 최솟값                  |
| max(s)       | 최댓값                  |
| s.count(x)   | x의 개수                |


non sequence container (중복 순서없음)

​	set, dictionary

​	중복제거하는방법 list -> set -> list



컨테이너형 형변환

string list tuple range(x) set dictionary(x)

dictionary는 key값만



* 데이터의 분류

  * mutable

    list dict set 사용자가만든데이터타입

  * immutable

    단일데이터들(숫자, 글자, 참거짓, range, tuple, frozenset)
