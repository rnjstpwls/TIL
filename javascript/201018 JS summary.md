# JS summary

* JavaScript로 할 수 있는 것
  * DOM (Document object Model) 조작
  * BOM (Browser Object Model) 조작
  * ECMAScript
* DOM(Document Object Model)
  * 문서를 다루기 위한 독립적인 문서 모델 인터페이스
* DOM Manipulation
  1. 선택
  2. 조작



1. 선택
   * 단일 노드 `document.querySelector()`
   * 여러 개의 요소 `document.querySelectorAll()`
2. 변경, 조작 (Manipulation)



### Evnet Listenter

* `addEventListener`

  `EventTarget.addEventListener(type, listener)`

* event.preventDefault()

  브라우저에서 동작하지 않도록 막는 행위





### AJAX (Asynchronous Javascript And XML)

* 서버와 통신하기 위해 XMLHttpRequest 객체를 사용하는 것
* 새로고침을 하지 않고 요청 작업을 비동기적으로 수행할 수 있다.



#### XHR(XMLHttpRequest)

* 서버와 상호작용하기 위해서 사용한다.
* 사용자가 하는 것을 방해하지 않고(새로고침 하지 않고) 페이지의 일부를 업데이트 할 수 있다.





#### JavaScript 의 특징

1. Asynchronous (기다려 주지 않는다.)
2. Single Thread (한번에 하나씩 동작한다.)
3. Event Loop
   * Call Stack
     * 함수의 호출을 기록하는 Stack
     * 한 번에 하나의 작업만 처리할 수 있다.
   * Web API
     * 브라우저에서 제공하는 API
   * Task Queue
     * Callback Function이 대기하는 Queue
   * Event Loop
     * Call Stack이 비어있으면 Task Queue의 함수를 Call Stack으로 보낸다.



#### Callback Function (다른 함수의 인자로 전달되는 함수)



#### 1급 객체

1. return 값으로 사용 가능
2. 함수의 인자로 사용 가능
3. 변수에 할당 가능

위 3가지 특징을 모두 만족하면 1급 객체라고 부른다.



#### Promise

> 비 동기 작업이 성공했을 때와 실패했을 때 결과를 약속하는 객체

1. 성공 `.then`
2. 실패 `.catch`



#### Axios

>  Promise 기반의 비동기 요청을 할 수 있는 JavaScript 라이브러리

