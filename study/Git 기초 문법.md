# Git 기초 문법	

> Git 분산형 버전관리시스템(DVCS)이다.



## Git 사전준비

0. (윈도우의 경우 : git bash를 설치한다.)

1. 로컬 설정

   ```
   $ git config --global user.name 'chanyoung98'
   $ git config --global user.email 'cksdud02@gmail.com'
   ```

* 처음 git을 설치하면, commit을 하는 작성자(author)를 설정해야 한다.

* email 정부는 github에 등록된 email을 설정하는 것을 추천.

* 설정된 내용을 확인하기 위해서는 아래의 명령어를 입력한다.

  ```bash
  $ git config --global -l
  user.name=chanyoung98
  user.email=cksdud02@gmail.com
  ```

* 오프라인 강의장에서 하는 경우 반드시 체크



## 기초흐름

> 작업 => add => commit
>
> 작업이 끝나면, 커밋할 파일을 모아(add) 커밋한다.(버전을 기록한다)

### 0. 저장소 설정



 ```bash
$ git init
Initialized empty Git repository in C:/Users/cksdu/.git/
 ```

* git 저장소로 활용하기 위해서는 위의 명령어를 활용한다.
  * .git 폴더가 생성
  * (master)로 현재 작업중인 브랜치 확인

### 1. add

> 커밋을 위한 파일목록(staging area)

```bash
$ git add .			  # 현재 디렉토리(임시저장)
$ git add a.txt		  # 특정 파일
$ git add a.txt b.txt # 여러 파일
$ git add md-images/  # 특정 폴더
```

> 실습

```bash
$ touch text.txt
```

> add 전 모습

```bash
$ git status
현재 브랜치 master
```

> add 후 모습

```
$ git add.
$ git status
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   test.txt

```

### 2. commit(본격적으로 올릴 준비가 되었다)

> 버전을 기록(스냅샷)

```bash
$ git commit -m 'first_commit'
[master (root-commit) e0a823b] first_commit
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test.txt

```

* 커밋 메시지는 현재 작업의 내용을 알 수 있도록 명확하게 작성한다.

* 커밋 이력을 확인하기 위해서는 아래의 명령어를 활용한다

  ```bash
  $ git log
  commit e0a823b759d6924c12b58e2e1738920a2c75a88b (HEAD -> master)
  Author: chanyoung98 <cksdud02@gmail.com>
  Date:   Sat Jan 23 20:24:46 2021 +0900
  
      first_commit
  
  ```

  * 추가옵션

    ```bash
    $ git log -l
    $ git log --oneline
    e0a823b (HEAD -> master) first_commit
    #head는 현재 있는거, master는 뿌리=시작점
    $ git log --oneline -l
    ```

    

### 3. 상태확인

> git 저장소의 현재 상태는 status로 확인하는 습관을 가지자.

```bash
$ git status
On branch master
nothing to commit, working tree clean
```

