### 안써봤던 파일들?

> apps.py tests.py asgi.py wsgi.py



* asgi.py	wsgi.py

asgi, wsgi 는 통신을 해주는 역할.

서버가 돌아갈 수 있게 해주는 역할. 추후에 배포를 할 때 사용



* apps.py
  * app 설정과 관련



### tests.py

https://developer.mozilla.org/ko/docs/Learn/Server-side/Django/Testing



자동화된 테스트는 첫번째 실전 고객으로 역할을 수행한다.



* TDD(Test-driven development, 테스트 주도 개발)
* BDD(Behaviour Driven Development, 행위 주도 개발)





* Unit tests(유닛 테스트)
  * 독립적인 콤포넌트의 (성능이 아닌) 기능적인 동작을 검증한다. 흔히 class나 function 레벨로 수행한다.



### 테스트 과정

###### ex) article create

* 서버를 킨다.
* /articles/create/
* 데이터를 입력한다.
  * 올바른 데이터
  * 올바르지 않은 데이터
* 저장을 누르고
* DB 새로운 article이 저장되었는지 확인.



```python
class YourTestClass(TestCase):
    def setUp(self):
        # Setup run before every test method.
        pass

    def tearDown(self):
        # Clean up run after every test method.
        pass

    def test_something_that_will_pass(self):
        self.assertFalse(False)

    def test_something_that_will_fail(self):
        self.assertTrue(False)
```



___

#### 작업순서

프로젝트 생성 pjt

앱생성 accounts, todos

url분리

template base.html생성

accounts/models.py 에서 abstract User 만들고 settings.py에 auth_user_model 추가

migrate

tests.py에 코드 복붙

`python manage.py test`



#### *<u>**서버를 키지않고도 코드로 동작하는지 점검을 할 수있다**</u>*

___

