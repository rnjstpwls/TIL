## Web Summary

* HTML (Hyper Text Markup Language)



* 시멘틱 태그
  * 장점
    * 읽기가 쉬워진다.
    * 접근성이 좋아진다.



* form 태그
  * action
  * method (GET POST)



* CSS (Cascading Style Sheets)
  * 우선순위
    1. !important
    2. inline
    3. id 선택자
    4. class 선택자
    5. 요소선택자
  * 상대크기
    * px % em rem
  * Box model
    * Margin Border Padding Content
    * 축약형



* 선택자 : 특정한 요소를 선택하여서 스타일링을 하기 위해 반드시 필요함.

  * 기초 선택자

    * 타입(요소,태그) 선택자, 아이디 선택자, 클래스 선택자, 전체 선택자

  * 고급 선택자

    * 자손 선택자 : 하위의 모든 요소 (띄워쓰기로 구분)

      선택자1 선택자2 { 속성: 속성값 }	`article p { color: red; }`

    * 직계 자손 선택자 : 바로 아래의 요소 ( > 로 구분)

      선택자1 > 선택자2 { 속성: 속성값} `div > p { color: blue; }`

    * 형제 요소 선택자 : 같은 레벨에 있는 요소 ( ~ 로 구분)

      선택자1 ~ 선택자2 { 속성: 속성값} `p ~ section { color: yellow; }`

    * 인접 형제 요소 선택자 : 바로 붙어 있는 형제 요소 ( + 로 구분)

      선택자1 + 선택자2 { 속성: 속성값} `div + p { color: purple; }`



* Box-sizing
  * box-sizing: border-box



* CSS position
  * static(default)
  * relative
  * absolute
  * fixed



* Float
  * none left right



* Flexbox
  * 요소
    * Flex Container
    * Flex Item
  * 축
    * main axis
    * cross axis
  * 속성
    * flex-direction
    * justify-content
    * align-itmes, align-self, align-content



* order
  * 기본값 0



* flex-grow
  * 남은 여백을 쪼개서 분배



* grid system
  * flexbox를 기반으로 12개의 column 시스템을 가짐.
  * 왜 12개 : 12가 약수의 갯수가 많아서 사용하는 경우의 수를 많이 고려 할 수 있음.
  * container > row > col
  * break point
    * sm (576px) / md (768px) / lg (992px) / xl (1200px)