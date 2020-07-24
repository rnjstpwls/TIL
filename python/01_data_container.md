### 01_data_container (수정)

___

컨테이너는 Sequency 형과  Non-sequence 형으로 구분할 수 있다.



* 시퀀스(sequence)형 컨테이너

  시퀀스는 순서대로 나열된(ordered)형식을 나타낸다.

  * 리스트(List)

    : [], list()

    

  * 튜플(tuple) - immutable (read only)

    : ()

    

  * 레인지(range)

    : range(n)					  0 to n-1

    : range(n, m)				n to m-1

    : range(n, m, s)			n to m-1, +s만큼 증가

    

  * 문자형(string)

  * ~~바이너리(binary)~~



* 비시퀀스(Non-sequence)형 컨테이너

  * 셋(set)

    : set(), 중괄호{}를 묶어서 사용

    ```python
    set_a - set_b	# 차집합
    set_a | set_b	# 합집합
    set_a & set_b	# 교집합
    ```

    

  * 딕셔너리(dictionary)

    : {}, dict()

    {key:value}

    key와 value를 함께 접근하는 방법

    ```python
    for a, b in enumerate(dic):
    ```

    > 여기서 a는 0, 1, 2, 3, 4를 의미하고 b는 key값들을 의미한다
    
    .items()를 활용할 수 있다.
    
    ```python
    for key, value in dic.items(): 
            if value == 50:
                return key
    ```
    
    

___

#### 정리

* 데이터는 sequence형과 non-sequence형으로 분류한다.
* 데이터는 mutable데이터와 immutable데이터로 분류한다.



| mutable                                                      | immutable                                                    |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| list()<br />dict()<br />set()<br />사용자가 만든 데이터 타입 | 숫자(Number)<br />글자(String)<br />참/거짓(Boolean)<br />range(), tuple(), frozenset() |



