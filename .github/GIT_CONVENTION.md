## 목차
- [Repository](#Repository)
- [Branch](#Branch)
- [Commit Message](#Commit-Message)
- [Issue](#Issue)
- [Pull Request](#Pull-Request)
- [작업 흐름](#작업-흐름)
  * [1. Issue를 만든다]
  * [2. 로컬에서 브랜치를 만들고 checkout]
  * [3. 작업을 한다.]
  * [4. commit message]
  * [5. push]
  * [6. PR 만든다]
  * [번외1) 커밋 메세지를 실수했다면?]
  * [번외2) 리뷰하기]
  * [번외3) 머지 종류]
  * [번외4) 작업을 하고 있는데, 누가 머지하라고 한다면? OR 다른 브랜치로 이동하고 싶은데, 지금하고 있는 작업이 아직 덜 끝남]

## Repository

1. `harmonica-template`을 template으로 repository 생성
  - 반드시 [Include all branches] 체크
    ![image](https://github.com/Harmonica-OIDC2023/.github/assets/68985625/7fd65454-0f22-4f0d-8388-055252833665)

2. `develop` 브랜치를 생성하고 default로 지정
  - Settings > Default branch에서 default 브랜치를 main → develop 으로 변경
    ![image](https://github.com/Harmonica-OIDC2023/.github/assets/68985625/0eefe066-dfc1-4b49-800e-2cc33469344c)
  
    

3. `develop`에 Branch protection rule을 Create
  - Settings > General > Code and automations > Branches 
  - [ ] **Require a pull request before merging**
    ![image](https://github.com/Harmonica-OIDC2023/.github/assets/68985625/7d3746e2-27c7-4586-bf7a-687242c1f473)
  - 체크 후 하단의 [**Create**] 클릭

4. Issue를 위한 Label들 생성
  - `Add`, `Fix`, `Doc`, `Style`, `Refactor`, `GC`
    ![image](https://github.com/Harmonica-OIDC2023/.github/assets/68985625/1b16a058-3c11-453b-966f-91bbccd33497)
    
    ![image](https://github.com/Harmonica-OIDC2023/.github/assets/68985625/1833349e-e9d2-413b-85b8-da90bdb6fea1)
 
## Branch

- main: 버전 관리 (추후 버전1, 2, 3)
- develop: 개발 관련 메인
- feat/#{이슈번호}
    - `feat/#6`

## Commit Message

Commit은 영어로, Issue/PR은 한글

1. 제목과 본문을 한 줄 띄워 분리하기
2. 제목은 영문 기준 50자 이내로
    - Add: 새로운 기능 추가
        - ✨ `:sparkles:`
    - Fix: 버그 수정
        - 🐛 `:bug:`
    - Doc: 문서 수정
        - 📝 `:memo:`
    - Style: 코드 포맷팅, 코드 변경이 없는 경우
        - 🎨 `:art:`
    - Refactor: 코드 리팩토링
        - ♻️ `:recycle:`
    - GC: 알콜코딩
        - 🍻 `:beers:`
3. 제목 맨 앞에 [브랜치 이름]
4. 제목 첫글자를 대문자로
5. 제목 끝에 `.` 금지
6. 제목은 `명령조`로
7. 본문은 영문 기준 72자마다 줄 바꾸기
8. 본문은 `어떻게`보다 `무엇을`, `왜`에 맞춰 작성하기

ex) 

```
[feat/#2] 영어동사: 작업
- description
---
[feat/#2] Fix: A to B
- 어쩌구
```

## Issue

- 제목 형식
    
     ex) 데이터 수집
    
- 큰 기능별 이슈 생성
    - 이슈에 체크박스로 해야할 일 작성(template 참고)
    
    → 큰 기능을 이슈로 만든 후 (하지만 너무 추상적은 X, Collect 이런식 X) 해당 이슈와 관련된 세부 태스크를 체크박스로 작성
    
    - 태스크:커밋=1:1

ex)

```
## 내용

ISSUE의 내용을 적어주세요.

## 작업 내용

- [ ] Todo 1
- [ ] Todo 2

## 참고 사항
```

- 작업 이슈말고 질문사항, 논의사항이 생기면 이슈에서 관리해도 좋음
    - 근데 마땅한 해결책이 없으면 머쓱한 이슈가 되므로, 상의한 것들을 이슈로 기록 남기는 것도 괜찮을듯
- 이슈 생성후 라벨 붙여서 가시화 (ADD, FIX, …)
- 1번 이슈는 github convention 관련으로!

## Pull Request

- 제목 형식
    - ex. ISSUE와 동일 혹은 비슷하게
- 첫번째 Comment에서 대응되는 issue와 연결
    - 이슈:PR=1:1
    - 본문에 `resolves: #{이슈 번호}` 추가하면 연결됨(template 참고)
- 이후 관련 커밋부터는 변경된 사항/추후 수정해야할 사항 작성

ex)

```
## 작업 내용

resolves: #{이슈번호}

## 참고 사항

PR을 리뷰할 때 중점적으로 리뷰가 필요하거나 참고가 필요한 내용을 적어주세요.
```

- PR 역시 라벨 달기
- Assignee(1명)를 정하고 리뷰를 부탁한다.
- 리뷰 후 Assignee가 확인하면 머지한다. 셀프 머지 금지

## 작업 흐름

### 1. Issue를 만든다

- 작업 단위로 만든다
- Assignees, Labels: 할당

![image](https://github.com/Harmonica-OIDC2023/.github/assets/68985625/cdea071c-3e35-4229-905b-a692f2a52c87)

### 2. 로컬에서 브랜치를 만들고 checkout

```bash
git branch feat/#{이슈번호}
git checkout feat/#{이슈번호}
```

### 3. 작업을 한다.

```bash
git add nayeon.txt
...
# git add . 는 반드시 지양한다 제발!
```

### 4. commit message

```bash
git commit -m "[feat/#{이슈번호}] :sparkles: Add: nayeon.txt files"
```

- 깃모지는 위에 참고

### 5. push

```bash
# 처음 로컬에 있는 브랜치 업로드할 때 --set-upstream 옵션을 해줘야 함
# 나중에 PR merge하고 remote에 있는 브랜치 삭제하면 깔끔스
git push --set-upstream origin feat/#{이슈번호}
```

### 6. PR 만든다

![image](https://github.com/Harmonica-OIDC2023/.github/assets/68985625/62f18822-cde5-4e10-afd3-5aef35f5d154)

### 번외1) 커밋 메세지를 실수했다면?

#### 1. git log

```bash
# 맨 위에 있는 것만 덮어쓸 수 있다.
```

#### 2. amend 옵션으로 다시 commit 한다

```bash
git commit --amend -m "[feat/#{이슈번호}] :sparkles: Add: nayeon.txt files"
# git log로 다시 확인
```

#### 3. force push

```bash
git push -f
```

### 번외2) 리뷰하기

- Approve를 해야 머지할 수 있음
![image](https://github.com/Harmonica-OIDC2023/.github/assets/68985625/d710a3b0-1e08-4988-838e-164c3eba2781)
- Looks Good To Me ~

### 번외3) 머지 종류

- Rebase and merge로 한다
- conflict가 나면 Rebase가 안 돼서 그냥 commit message 들어가는 걸로 하기!
- 머지하고 나서 필요 없으면 브랜치 바로 지우는 버튼 누르면 됨

### 번외4) 작업을 하고 있는데, 누가 머지하라고 한다면? OR 다른 브랜치로 이동하고 싶은데, 지금하고 있는 작업이 아직 덜 끝남

- git stash

```bash
git stash
# 현재 변경사항들(git status로 보이는)이 temp 디렉토리에 저장 돼
git stash list # 리스트를 볼 수 있고
... # 브랜치를 옮기거나.. 작업을 하고
git stash apply # 변경사항 적용
```
