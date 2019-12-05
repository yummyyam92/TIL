# Git

> git은 분산형버전 관리시스템(DVCS)이다.
>
> 소스코드 형상 관리 도구로, 코드의 이력을 관리할 수 있다.

## Git 로컬 저장소 활용하기

> git은 `repository(저장소)'로 각각 프로젝트를 관리 한다.

### 0. 기본 설정

Git에서 이력을 남기기 위해 잘성자(author) 정보를 추가한다. 매 컴퓨터에서 최초로 한 번만 설정하면 된다.

```bash
$ git config --global user.name {유저네임}
$ git congig --global user.email {이메일}
```



* 일반적으로 `{유저네임}`, `{이메일}`에는 github정보를 넣는다.

### 1. 저장소 생성

```bash
$git init
Initialized empty Git repository in C:/Users/student/Desktop/TIL/.git/
(master)$
```



## 2. add

> 커밋대상 파일을 staging area로 이동시킨다.
>
> 즉, 이력을 남길 파일을 담아놓는 것이다.

```bash
$ git add . #현재 디렉토리 모두 stage
$ git add git. md #특정 파일만 stage
$ git images/ #특정 폴더만 stage
#위에 세개 같은 말
#.은 현재 디렉토리(폴더)를 뜻한다
#항상 `git status`명령어를 통해 상태를 확인하자
$ git status 
```



## 3. commmit

> git에서 이력을 남기기 위해서는 커밋을 진행.

```bash
$ git commit -m 'Git 기초'

[master (root-commit) 9c20af8] Git 기초
 3 files changed, 59 insertions(+)
 create mode 100644 Git.md
 create mode 100644 "images/\353\247\210\355\201\254\353\213\244\354\232\264 \355\231\234\354\232\251\353\262\225.jpg"
 create mode 100644 "\353\247\210\355\201\254\353\213\244\354\232\264 \355\231\234\354\232\251\353\262\225.md" (master)$

```

> 이력을 확인하기 위해서는 git log를 활용한다.

```bash
$ git log
commit 9c20af84194c3ecdcf3e12c7b7c11f78aee4fb7d (HEAD -> master)
Author: yummyyam92 <yummyyam92@gmail.com>
Date:   Thu Dec 5 12:41:26 2019 +0900

    Git 기초 


```

# Git 원격 저장소 활용하기

## 0. 기본 설정

> 원격 저장소를 생성한다. (예 - github)



## 1. 원격 저장소 등록

origin`이라는 이름으로 해당 url을 원격 저장소로 등록

최초에 한번만 하면 된다.

```bash
$ git remote add origin https://github.com/yummyyam92/TIL.git

```

```bash
$ git remote -v #원격 저장소 목록
origin  https://github.com/yummyyam92/TIL.git (fetch)
origin  https://github.com/yummyyam92/TIL.git (push)

```

## 2. 원격 저장소 push

앞으로 변경되는 사항이 있으면 항상 add, commit, push를 진행한다.

```bash
$ git push -u origin master
```

