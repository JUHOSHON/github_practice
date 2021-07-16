# 백업

1. 원격 저장소 생성

2. remote 정보 입력
3. git push



## 백업 용어 정리

* 내가 사용하는 컴퓨터 : `local repository`
* 로컬 저장소에서 업로드해서 로컬 저장소와 똑같은 상태를 유지하는 저장소 : `remote reposiotry`
* local -> remote 업로드 하는 과정 : `PUSH (백업)`
* 원격 저장소를 로컬 저장소로 복제해오는 것(복원) : `CLONE`
* 로컬에서 원격의 버전을 다운 받는 것 : `PULL`



## git hosting

원격 저장소를 마련하는 것(서비스를 제공받아야된다.) == github



## 원격저장소와 연결

### git remote

원격 저장소 정보 출력

* git remote add : 지역저장소와 원격저장소를 **연결**
  * git remote add [저장소별명]  [저장소 주소]
    * git remote add origin https://github.com/JUHOSHON/review.git
  * git remote 하면 origin이 출력됨
  * git remote -v 하면 상세한, 구체적인 내용이 출력됨



### git push

원격 저장소에 코드 업로드

* git push  --set upstream [저장소 별명] [브랜치 이름]
  * enter 후 이메일을 치면 업로드 성공
  * 한 번만 입력하면 그 후부턴 git push만 입력해도 자동으로 그곳에 저장됨



# 복원

* 새 컴퓨터에 작업물을 복제해서 복원하는 것



### clone

* git clone [원격저장소 주소]



## pull

* 원격저장소의 버전을 지역저장소로 가져오는 방법



### git pull



## 작업의 순서

* 언제나 `pull -> 작업 -> commit -> push`





