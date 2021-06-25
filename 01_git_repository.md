# GIT 초기 설정

커밋 작성자 설정

```bash
# 명령을 시키고자 하는 주체
# git아, 전역 설정중, 유저의 email을 설정 할거야.
$ git config --global user.email junelee444@naver.com
# git아, 전역 설정중, 유저의 name을 설정 할거야.
$ git config --global user.name mulcambeginner
```

- 커밋을 작성하는 사람이 누구인지 알아야하기 때문에

지정된 설정 확인

```bash
# git아 현재 전역에 설정된 설정 목록 보여줘
$ git config --global -l
# $ git config -- global --list
```

# Git Basic

# 로컬 저장소 설정

```bash
$ git init
```

- 폴더에 git 저장소를 초기화하면, 

  - .git이라는 숨김 폴더가 생기고
  - bash에는 (master)라는 표기가 생성된다.

  

- 주의사항

  - .git 폴더를 직접적으로 수정하는 일은 없을 것이다.
  - 이미 git으로 관리하고 있는 (bash창에 master가 표기되어 있는 폴더내에서는 절대 git init하지 말 것)

  # status

  ```bash
  # git아 너가 관리중인 폴더의 상태 보여줘
  $ git status
  ```

  # add

  ```bash
  $ git add 파일명
  $ git add . # 현재 디렉토리
  $ git add a.txt # 특정 파일
  $ git add directory_name/ # 특정 폴더가 가진 모든 파일
  ```

- working directory 상태의 파일을 staging area 상태로 변경
- 커밋을 위한 파일 및 폴더들을 추가하는 명령어

## commit

```bash
# git아, commit 할건데 -메세지는 "이걸로 해줘"
$ git commit -m "commit message"
# git commit -m "210624 | created CLI.md"
```

- 커밋을 통해 하나의 버전으로 기록됨
- 커밋 메세지는 현재 변경사항들을 잘 나타낼 수 있도록 작성하는 것을 권장
- 커밋 목록은 git log를 통해서 확인 할 수 있음

```bash
$ git log --oneline
```

## 원격저장소(remote repository)

# 기본 설정

1. 로컬 git 저장소 준비
2. github repository 생성
3. Repository default branch 변경



## 명령어

### 원격 저장소 주소 추가

```bash
# git아, 원격 저장소 주소 origin 이라는 이름으로 추가 할건데
# 주소는 이거야.
$ git remote add origin https://github.com/mulcambeginner/github_study.git
```



### 원격 저장소 목록 보기

```bash
$ git remote -v
```



### 원격 저장소 삭제

```bash
$ git remote rm origin
```



### 원격 저장소에 업로드(push)

```bash
# git아 업로드 할건데 origin이라는 이름으로 저장해둔 원격저장소에 master 브랜치의 commit 내역들을 업로드 할거야.
$ git push -u origin master
```

- commit 내역이 없으면 업로드 불가능



### clone

- 원격 저장소 내용 전체 복제

```bash
# git아, 전체 내용 복제 해줘
$ git clone {원격저장소 url}
```

- 주의사항 
  - 이미 git init이 되어있음



### pull(허브 다운로드)

- 원격 저장소의 변경사항을 받아옴(업데이트)

```bash
$ git pull origin master
```

- 변경사항 맞춰서 다운로드





