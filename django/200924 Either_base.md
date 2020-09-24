

## 처음부터 Either 작성

1. 가상환경 설정
   * django 설치

2. 장고 프로젝트 만들어주세요.
   * 프로젝트명 : **balance_game**
   * 앱 명 : **eithers**
3. urls.py 분리 / 기본 template(base.html)
   * urls 분리
   * base.html (부트스트랩 CDN 포함)
     * settings.py 에 등록.

유저와 관련된 내용이 있다면

​	custom User 적용.

___

## 모델 정의 (models.py)

* 투표 모델

  * 주제
  * 항목 2개
  * migration 작업

* 댓글 모델

  * 댓글 입력창
  * 어떤 글의 댓글인지 FK 설정.

  



## 폼 정의 (forms.py)

* 투표 모델을 기반으로 폼 정의
* 댓글 모델을 기반으로 폼 정의



## 기능 정의

* 투표 모델은 생성과 조회 (CR)

  * CREATE
  * READ

  

* 댓글 모델 생성과 조회 (CR)



`pip install django-bootstrap4`