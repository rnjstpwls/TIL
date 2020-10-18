# Git

> Git은 분산버전관리시스템(DVCS)이다. Distributed Version Control System
>
> 소스코드의 버전 및 이력을 관리할 수 있다.

## 준비하기

윈도우에서 git을 활용하기 위해서 [git bash](http://https//gitforwindows.org/)를 설치한다.

**초기 설치**를 완료한 이후에 컴퓨터에 `author`정보를 입력한다.

```bash
$ git config --global user.name {user name}
$ git config --global user.email {user email}
```

## 로컬 저장소(repository) 활용하기

### 1.저장소 초기화

```bash
$ git init
Initialized empty Git repository in C:/Users/student/Desktop/TIL/.git/
```

- `.git`폴더가 생성되며, 여기에 git과 관련된 모든 정보가 저장된다.
- git bash에 `(master)` 라고 표시가 된다.

### 2. add

`working directory (작업공간)`변경된 사항을 이력으로 저장하기 위해 반드시 `staging area`에 올려야 한다.

```bash
$ git add git_정리.md # 특정 파일
$ git add python/ # 특정 폴더
$ git add . # 현재 디렉토리의 모든 파일
```

### 3. Commit

- 버전의 이력을 확정짓는 명령어, 해당 시점을 스냅샷으로 만들어서 기록을 한다.

- 커밋시에는 반드시 log 메세지를 작성해야하며, log 메세지는 변경사항을 알 수 있도록 명확하게 작성해주면 된다.

  ```bash
  $ git commit -m '깃 정리 문서 작성'
  ```

------

## 원격 저장소 (GitHub / GitLab)

### 0. repository 생성

### 1. 원격 저장소를 local 에 등록

```bash
$ git remote add origin '깃 레파지토리 주소'
$ git remote -v # 현재 등록된 remote 정보를 확인 가능.
```

### 2. Push

- 원격 저장소로 업로드

```bash
$ git push origin master
```

------

### 우리의 루틴

- 집에서 한것이 최신 버전이고 싸피에서 git 작업을 한 번도 하지 않은 경우

  1. ```bash
     git clone '원격 저장소 주소(레파지토리 주소)'
     ```

     - 원격 저장소를 기준으로 최신 버전의 파일이 다운로드 받아짐
     - .git 폴더도 자동 생성되어 짐. (git DB 가 들어 있기 때문)

  - add , commit , push 루틴은 아래와 같음

- 집에서 한 것이 최신 버전이고 집에서 작업을 하는 경우

  `add -> commit -> push`

- 싸피에서 한 것이 최신 버전이고 집에서 작업을 하는 경우

  `pull -> add -> commit -> push`

  `git pull origin master`

  해당 루틴으로 진행하면 끝!

___

#### 20200731 추가

```bash
# 버전관리
$ git init
$ git add .
$ git commit -m 'add a.txt'


# 상태확인
$ git status


$ git log
한줄로 보고싶을때
$ git log --oneline

과거의기록과 최근에 수정된 기록이 어떻게 다른지 보고싶을 때
$ git diff

# 되돌리기
빼고싶을때 (add 햇는데 취소하는법)
(use "git restore --staged <file>..." to unstage)
$ git restore --staged b.txt

(commit 햇는데 수정하는법) -> 웬만하면 쓰지말자. commit은 신중하게 하자.
$ git commit --amend
맨위에꺼만 수정가능

```

___

#### 20200918 Branch



# branch

> git branch 명령어 정리



## 개념

- 나무가지라는 의미로 코드의 분기를 의미함



## 확인

- `git branch`



## 생성

- `git branch <new branch name>`



## 이동

- `git switch <branch name>`



## 삭제

- `git branch -d <branch name>`



___

#### 201016 추가
GIT banch



(협업/분업) => 이상적인 개발흐름





두 사람이 어떻게 코드를 나누고 그것을 합치는가



가정) 역할부여

A : 리더(PL), B : 조원

1. 프로그램을시작할 수 있도록 리더가 첫 커밋을 찍어둔다. 그리고 그것을 공유할 수 있는 사이트에 공유한다.
2. 그리고 B에게 프로젝트 권한을 부여해 준다.(Maintainer)
3. 그리고 B가 클론을 떠서 가져온다.
4. 가정) nav bar를 변경한다고 가정
5. `git branch feature/nav` 로 branch 생성
6. `git branch` 로 생성되었는지 확인
7. `git switch feature/nav` upload할 git 변경
8. `git add . `
9. `git commit -m 'nav info fix'`



B는 footer를 수정한다고 가정.

1. `git branch feature/footer`
2. `git switch feature/footer`

3. add commit



##### GIT LAB 이 가지고 있는 기능 사용

feature/nav 라는 branch와 feature/footer 라는 branch를 gitlab에 upload

A

`git push origin feature/nav`

feature/nav라는 branch가 upload됨.

but master에는 변화가 없다.

새롭게 코드가 추가된건 feature/nav임



B

`git push origin feature/footer`



총 3개의 branch가 있다.

gitlab 사이트에서 branch누르고 `비교` 눌러보면 원래코드에서 어디가 어떻게 변경되었는지 확인할 수 있다.

`머지 리퀘스트(MR) 만들기`를 누르면 master로 병합해달라는 요청을 보낼 수 있다.

`merge` 버튼을 누르면 최종으로 통합된다. (master 로 합쳐지고 기존 branch는 삭제시키면 된다.)

이제 각각 A. B 사용자가 최신 master를 받아와야한다.

A

`git switch master`

`git pull origin master`



`git branch -d feature/nav` feature branch 삭제



B도 반복



___



### 충돌이 나는 상황을 가정

가정) A, B가 같이 Title 정보를 수정한다고 가정

A

`git branch feature/title`

`git switch feature/title`

add commit



B

`git branch feature/title-ko`

`git switch feature/title-ko`

add commit

`git push origin feature/title-ko`



A는 정상적으로 merge되지만 B를 머지요청보내면

`! 머지 충돌이 있습니다`

충돌이 난 경우 회의를 통해 택 1을 해야한다.

다시 commit을 하고 (사이트에서 바로 가능함)

새로고침을 하면 이제 머지할수있다고 뜸.
___

