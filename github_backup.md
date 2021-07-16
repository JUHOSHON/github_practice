# CLI

command Line Interface

커맨드(명령어)를 통해 작동하는 인터페이스

<-> GUI(Graphic User Interface, 보통의 프로그램)



## 기초 명령어

#### (1) `pwd`

* `pwd` (print working directory) : 현재 폴더의 경로
* `~` (home directory) : 홈 디렉토리(git bash 처음 열면 나오는 기본 폴더)



#### (2) `ls`

* `ls` (list) : 내용물을 출력(list)



#### (3) `cd [폴더명]`

* `cd` (change directory) : 폴더를 변경
* `cd ..` : 상위 폴더로 이동
* `cd .` : 현재 폴더로 이동



#### (4) `mkdir [폴더명]`

* mkdir(make directory) : 폴더를 생성



#### (5) `rm [파일명]`

* `rm` (remove) : 파일을 삭제



#### (6) `rm -r [폴더명]`

* `-r` : recursively(재귀적으로) 폴더를 삭제



#### (7) `touch [파일명]`

* touch : 파일 생성



#### (8) cp [파일명] [위치]

* `cp`(copy) : 파일 복사



#### (9) cp -r [폴더명] [위치]

* 폴더를 복사



#### (10) mv [파일/폴더명] [바꿀파일/폴더명]

* `mv` (move) : 파일/폴더명 변경
* `mv` [파일/폴더명] [위치] : 파일 또는 폴더를 이동

# Git

(**버전**을 통해) 코드 관리 도구



# SCM & VCS

* SCM : Source Code Management(소스 코드 관리)
* VCS :  Version Control System(버전 관리 시스템)
* DVCS : Distributed VCS(분산형 버전 관리 시스템)



# Git?

* 버전 관리 도구
  * 변경 이력 트래킹
  * 언제든 특정 시점으로 이동 가능
* 백업 도구
* 협업 도구



# Git 버전관리

> 중요 : Git은 폴더 단위로 코드를 관리

* 커밋 == 버전 생성 == 스냅샷 촬영 == 현재상태 저장



# git의 작동원리

![git_graphic](https://user-images.githubusercontent.com/87507463/125960141-4bf12cd3-9224-417b-8a59-a27ba1e50766.jpeg)





# `git init `

특정 폴더를 git으로 관리 시작

* (master) 프롬포트에 표시
* `.git ` 폴더 생성
  * `.git` 폴더 삭제시 git관리 중지`(rm -r .git)`



# `git status`

git에게 상태 확인

* `git init` 직후

```
On branch master : master라고 하는 branch에 있어

No commits yet : 아직 commit 없어

nothing to commit (create/copy files and use "git add" to track)

: commit 할게 없어 (트래킹 하고 싶으면 `git add` 명령어 사용해')
```



* a.txt 파일 생성 직후

```
Untracked files:  추적되지 않은 파일이 있어
  (use "git add <file>..." to include in what will be committed)
        a.txt(빨강)
commit 될 수 있게 포함하고 싶으면 git add <파일명>을 사용해
nothing added to commit but untracked files present (use "git add" to track)
```



* `git add a.txt`직후

```
Changes to be committed: commit 될 변경 사항이 있어
  (use "git rm --cached <file>..." to unstage)
        new file:   a.txt(초록)
```



# `git add [파일명]`

Staging Area(스냅샷 무대)에 파일 추가



# `git commit -m "커밋 메세지"`

버전을 생성

* 커밋(버전) 구성 요소
  * 해쉬(hash)
  * 작성자
  * 날짜
  * 커밋메세지 : 버전에 대한 설명



# `git log`

버전(커밋)들의 히스토리(로그)

* `git log --oneline`을 하면 그동안 저장된 버전들을 한눈에 보기 쉽게 출력



# `git config`

설정

* git config [설정할 내용] [설정할 값]
  * git config user.name '깃허브 이름'
  * git config user.email '깃허브 이메일'
  *  git config --global : 전역 설정

```
Author identity unknown  작자 미상

*** Please tell me who you are. : 네가 누군지 말해주세요

Run  다음을 실행하세요

  git config --global user.email "you@example.com"
  git config --global user.name "Your Name"

to set your account's default identity.
Omit --global to set the identity only in this repository.

fatal: unable to auto-detect email address (got 'SHON@DESKTOP-FSB8L1D.(none)')

```





# 백업

1. 원격 저장소 생성

2. remote 정보 입력
3. git push



## 백업 용어 정리

* `local repository` : 내가 사용하는 컴퓨터
* `remote reposiotry` : 로컬 저장소에서 업로드해서 로컬 저장소와 똑같은 상태를 유지하는 저장소 
* `PUSH (백업)` : local -> remote 업로드 하는 과정 
* `CLONE` : 원격 저장소를 로컬 저장소로 복제해오는 것(복원) 
* `PULL` : 로컬에서 원격의 버전을 다운 받는 것 



## git hosting

원격 저장소를 마련하는 것(서비스를 제공받아야된다.) == github



## 원격저장소와 연결

### `1. git remote`

원격 저장소 정보 출력

* git remote add : 지역저장소와 원격저장소를 **연결**
  * git remote add [저장소별명]  [저장소 주소]
    * git remote add origin https://github.com/JUHOSHON/review.git
    * `원격저장소 URL에 [저장소 별명] 으로 연결하겠다.`
  * git remote 하면 origin이 출력됨
  * git remote -v 하면 상세한, 구체적인 내용이 출력됨
  * 원격 저장소 별명은 중복될 수 없다.
  * 기존의 저장소 별명 지우기 : git remote remove [기존 저장소 별명]



### `2. git push`

원격 저장소에 코드 업로드

* git push  --set upstream [저장소 별명] [브랜치 이름]
  * remote repository가 디폴트 원격 저장소로 설정되는 것
  * enter 후 이메일을 치면 업로드 성공
  * 한 번만 입력하면 그 후부턴 git push만 입력해도 자동으로 그곳에 저장됨



## pull & push 구조

![pull and push](C:\Users\SHON\github\pull and push.jpg)



# 복원

* `git clone[원격저장소 주소]`
* 새 컴퓨터에 작업물을 복제해서 복원하는 것
* 내가 새 컴퓨터에서 작업을 하는 경우 한 번만 진행하면 된다.

* 원격 저장소 코드 다운로드



## pull

* `git pull [저장소 별명] [브랜치 이름]`
* 원격저장소의 버전을 지역저장소로 가져오는 방법
* 예시) 회사에서 작업하고 github에 push한 작업물을 집에서 받아서 작업하려는 경우





# 작업의 순서

* 언제나 `pull -> 작업 -> commit -> push`

  1. 사용자 폴더 내에서 git으로 활용할 폴더 생성 : `mkdir  [폴더명]`

  2. 생성한 폴더 내로 이동 : `cd [폴더명]/`

  3. git으로 관리 시작 : `git init` 이후 (master)가 붙는다

  4. 앞으로 작업할 파일을 저장하기 전에 `github`에 `repository`를 생성한다.

  5. 예) a.txt를 생성하기 : touch a.txt

  6. `Staging Area`로 이동 : `git add a.txt` / `git add .`를 하면 폴더 내 변경사항들을 모두 반영

  7. 버전 명을 지어준다 : `git commit -m "커밋 메세지"`

  8. git hub에 push한다. : `git push [저장소 별명] [브랜치 이름]`

     



