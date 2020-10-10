# SQL

* 기본키 : 각 행의 고유값
* 테이블 : 열과 행의 모델을 사용해 조직된 데이터 요소들의 집합
* 스키마 : 관계형 데이터베이스에서 구조와 제약조건에 관련한 전반적인 명세를 기술 한 것
* 레코드 : 단일 구조 데이터 항목을 가리키는 행
* 컬럼 : 고유한 데이터 형식이 지정되는 열



#### RDBMS, NOSQL

* RDBMS : Relational DataBase Management System
  * 테블묶음
  * 구조가 명확하게 정의 (엄격한 스키마)
  * 하나의 값만 저장
* NOSQL
  * 유연한 구조(유연한 스키마)
  * 데이터를 여러 테이블에 나누어 담지 않는다.



#### DDL DML DCL

* DDL (Data Definition Language) - 데이터 정의 언어

  > CREATE (생성)
  >
  > DROP (삭제)
  > ALTER (수정)

* DML (Data Manipulation Language) - 데이터 조작 언어

  > INSERT (생성)
  > UPDATE (수정)
  >
  > DELETE (삭제)
  >
  > SELECT (조회)

* DCL (Data Control Language) - 데이터 제어 언어

  > GRANT
  >
  > REVOKE
  > COMMIT
  > ROLLBACK



#### Example

* CREATE (테이블 생성)

  ```sql
  CREATE TABLE (테이블명) (
      컬럼명1 종류1 [제약조건],
      name TEXT NOT NULL,
      age INT,
      ...
  );
  ```



**[데이터타입 종류]**

> INT(INTEGER)
>
> CHAR(CHARACTER)
>
> VARCHAR
> FLOAT
> DATE
> TIME
> BLOB
> TEXT



* DROP (테이블 삭제)

  ```sql
  DROP TABLE (테이블명);
  ```



* ALTER (테이블 수정)

  ```sql
  ALTER TABLE (테이블명)
  RENAME TO (변경할테이블명);
  
  ALTER TABLE (테이블명)
  ADD COLUMN 컬럼명 종류 [제약조건];
  ```

  

* INSERT (데이터 입력)

  ```sql
  INSERT INTO 테이블명 (name, age, money)
  VALUES ('이름' , 20 , 1000)
  
  -- 모든 컬럼에 입력할때 가능
  INSERT INTO 테이블명
  VALUES ('이름' , 20 , 1000)
  ```

  

* UPDATE (데이터 수정)

  ```sql
  UPDATE (테이블명)
  SET 컬럼='변경값'
  WHERE 조건;
  ```

  

* DELETE (데이터 삭제)

  ```sql
  DELETE FROM (테이블명)
  WHERE 조건;
  ```

  

* SELECT (데이터 조회)

  ```sql
  SELECT 컬럼 FROM 테이블명 WHERE 조건;
  
  -- ex)
  SELECT * FROM 테이블명
  
  -- DISTINCT 하면 중복 제거
  SELECT DISTINCT age FROM 테이블명
  
  -- ORDER BY ASC // ORDER BY DESC
  -- LIKE (와일드카드) % _
  
  ```

  

