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



## branch command

- 브랜치 생성

```bash
$ git branch 브랜치명
```

- 브랜치 목록

```bash
$ git branch
```

- 브랜치 이동

``` bash
# git checkout 까지만 입력한 상태에서
# tab*2 -> checkout 가능한 브랜치명 확인 가능
$ git checkout 브랜치명
(브랜치명) $
```

```bash
$ git log --oneline
f55df98 (HEAD -> master, origin/master, origin/HEAD) modified o1_git_repository.md
```

- HEAD:현재 우리가 속한 위치

```bash
$ git log --all --graph --oneline
```

- 브랜치 생성+이동

```bash
$ git checkout -b 브랜치명
```

- 브랜치 병합

```bash
(master) $ git merge 브랜치명
```

반드시 master 브랜치에 브랜치를 병합

- 브랜치 삭제

```bash
$ git branch -d 브랜치명
```

- 브랜치 강제 삭제

```bash
$ git branch -D 브랜치명
```

merge가 되지 않은 브랜치는 강제로 삭제해야 함.



## 3가지 병합 상황

### 1.fast-foward

"다른 브랜치를 생성한 후,master 브랜치에 변경 사항이 없을 때"

### 2. 3-way Merge

"현재 브랜치(master)가 가리키는 커밋이 Merge 할 브랜치의 조상이 아니라면 깃은 현재 브랜치와 머지할 브랜치의 커밋 2개와 두 브랜치의 공통조상 하나를 사용한다."

### 1. 새로운 브랜치 sign up 생성

### 2. sign up 브랜치에서 signup.py 생성

- git add, commit 잊지 말기.

### 3. master 브랜치에서  new folder와 new.py 파일 생성

- git add, commit 잊지말기

###  4. master 브랜치와 sign up 브랜치 병합

###  5. sign up 브랜치 삭제



### 3.Merge Conflict

"두 개의 브랜치가 동일한 파일의 동일한 위치를 수정하고 merge 하려고 할 때 발생하는 현상"

단, 동일 파일을 수정했다고 하더라도 서로 다른 영역을 수정한다면 merge conflict는 발생하지 않는다."

- git이 자동으로 병합하지 못하는 상황

### 1. 새로운 브랜치 hotfix 생성

```bash
$ git branch hotfix
$ git checkout hotfix
# $ git checkout -b hotfix
```

### 2. hotfix 브랜치에서 b.txt에 새로운 내용 입력

- git add, commit

```bash
$ git add . or b.txt
$ git commit -m "message"
```

### 3.master 브랜치에서 b.txt에 새로운 내용 입력

- git add, commit

```BASH
$ git add . or b.txt
$ git commit -m "message"
```

### 4. master 브랜치와 horfix 브랜치 병합

```bash
```

