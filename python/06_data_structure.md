### Error & Exception

___

EOL (End Of Line)

EOL while scanning string literal



EOF (End Of File)



Exception

실행 도중 예상하지 못한 상황을 맞이하면, 프로그램 실행을 멈춥니다.

* ZeroDivisionError : 0으로 나누는 경우
* NameError : 선언하지 않은 변수를 사용한 경우
* TypeError : 자료형에 대한 타입 자체가 잘못 되었을 경우
* ValueError
* IndexError
* KeyError
* ModuleNotFoundError
* ImportError
* KeyboardInterrupt

> Ctrl + C 로 정지

외울수도없고 그럴필요도없고 하다보면 자연스레 습득될것



### 예외처리(Exception Handling)

`try` & `except`

에러 메시지 처리 `as`

`try` & `except` & `else`

`finally`



### 예외 발생 시키기 (Exception Raising)

`raise`



### 데이터구조(Data Structure)

___

Dictionary,, 문제해결을위한 데이터구조로 사용할 수 있다.





Harvard - CS50 강의는 좋은 강의이니 시간날때 들어보도록 하자.





* .find()

* .index()

* .replace(old, new[, count])

* strip ★ 잘쓰면 매우편하다.

* split() ★ input(입력값)받을때 매우 중요하다.

* 'separator'.join(iterable)

  



#### 리스트(List)

> 변경가능하고(mutable), 순서가 있고(ordered), 순회 가능한(iterable)



원본변경       => None

원본변경X    => 변경된 Data를 return



* .append(x)
* .extend(iterable)
* .insert(i, x)
* .remove(x)
* .pop(i)
* .clear()



#### 리스트 복사

잘 이해가 가지 않는다면 파이썬튜터를 사용해서 어떻게 자료값이 저장되는지 확인하자.



#### List Comprehension

잘 되지 않는다면 반복문으로 먼저 코드를 작성하고 한줄로 바꿔보는 과정을 하자.



___



set - 집합, 중복불가능하다.

dictionary 3.6버전부터 메모리관리차원에서 순서를 부여하는데

기본적으로 순서는없다 생각하자

.values()로 접근하면 value만 접근가능

.items()로 접근하면 key value접근가능 tuple로 저장하니 같이 쓰고 싶으면 2개 모두 할당하자.



##### 조회

.get ★★★ 굉장히 많이 사용한다.

##### 추가 및 삭제

.pop

.update -> key 값 'apple'아니고 그냥 apple로 써야되니 주의해서 쓰자.



