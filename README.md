# Today I Learned
> 매일매일 배운것을 기록합니다.

## 2022-09-13
### RPA 1기, 웹프로그래밍 기획과 기본
#### 리눅스 커맨드라인 기초
- `pwd`: print working directory의 약자로 현재 작업 경로를 출력해주는 명령어
- `cd`: change directory의 약자로 현재 작업 경로를 변경할 때 쓰는 명령어
  - 절대 경로는 `/`로 시작함
  - 상위 경로는 `..`으로 나타냄
  - `tab`을 사용하면 경로 자동 완성이 됨
- `ls`: list의 약자로 현재 작업 경로에 있는 파일이나 디렉터리를 출력해주는 명령어
  - `ls -a`, `ls -l`, `ls -al`과 같은 옵션을 붙일 수 있음
- `history`: 과거에 쳤던 명령어 리스트를 보여줌
  - 123번째 명령어를 복구하고 싶으면 `!123`입력
  
#### vim 사용법
- 명령 모드와 입력 모드
  - vim에디터를 열때는 명령 모드로 진입함
  - 명령모드에서는 입력이 불가능
  - 입력을 하려면 입력모드로 바꿔야 함
    - 키보드에서 `i` 누름
  - 입력이 끝나고, 저장하고 나오려면 명령 모드로 바꿔야함
    - 키보드에서 `ESC` 누름
  - 입력 가능한 명령어
    - `:w`: 저장하기
    - `:q`: 나오기
    - `:wq`: 저장하고 나오기
  - 참고자료 [링크](https://zeddios.tistory.com/122)
- 비정상적으로 종료시 해결 방법
  - vim이 비정상 종료 되었을때 `swp` 파일이 생성됨
    - ATTENTION 문구가 뜨는 경우
      1. 두 프로세스, 두 사람이 동시에 한 파일을 수정하는 경우
      2. crash가 나서 vim이 비정상적으로 닫힌 경우
  - 기존에 입력했던 내용을 복구하고 싶을때는 `vim -r 파일명`을 입력하거나 Recovery모드로 진입
  - 정상 종료 후, `swp` 파일 삭제
    - `rm .789.txt.swp` <-- `rm` 명령어는 remove 약자

#### 마크다운 문법
- 외부 링크 추가
```
사용문법: [Title](link)
적용예: [Google](https://google.com, "google link")
```
Link: [Google](https://google.com, "google link")

#### 버전 관리 시스템과 git

##### 버전 관리 시스템을 사용하는 이유
1. 실행 취소, 재 실행기 가능함
2. 버전간 소스코드 비교가 가능함
3. 협업이 쉬워짐

##### 다양한 버전관리 방법
이름 변경하기 등의 방법이 있는데, 개발할 때는 git을 주로 사용함

##### 커밋
- 커밋은 논리적 변경이 있을 때 만듬
- 가능하면 커밋 크기가 작을수록 좋음

###### 커밋 이력 보기
```
git log
```

##### 리포지토리
- 정의: 여러 파일을 하나로 모은 컬렉션
- 일반 디렉터리와 리포지토리의 차이: `.git` 디렉터리 유무

#### 저장소 상태 파악하기

```
git status
```

## 2022-09-20

### 브랜치
- 정의: A branch in Git is simply a lightweight movable pointer to one of these commits.
- 브랜치는 특정한 목표를 가지고 코드를 수정할 때 주로 만듬
  - 이슈 하나당 브랜치 하나를 주로 만듬

#### 명령어
1. 브랜치 목록 보기
```
git branch
```

2. 브랜치 생성 하기
```
git branch 브랜치명
```
3. 특정 브랜치로 전환하기
```
git checkout 브랜치명
```
or
```
git switch 브랜치명
```
4. 브랜치 생성과 체크아웃 동시에 하기
```
git checkout -b 브랜치명

```


# 2022-09-27
## 브랜치 병합

- 명렁어
```
git merge 브랜치명
```

# 2022-10-11
## 깃의 인증 방법
- ID/PW 방식
- 키 방식(공개키/개인키)
- 토큰 방식(personal access token)

## 지금까지 배운 명령어 개념과 함께 복습
  - git commit, git branch, git checkout, git checkout -b, git merge, git pull
  - 참고 사이트: https://violet-bora-lee.github.io/git-tutorial/

## git merge 방식
1. 3-way
2. fast-forward

## git push시 내부에서 일어나는일
- (현재 main 브랜치를 체크아웃하고 있다는 가정하에) git push origin main을 입력하면, 로컬저장소에 있는 main브랜치에 있는 모든 커밋이 원격저장소(origin)에 있는 main 브랜치로 병합이되는데, 이때 방식은 fast-forward임