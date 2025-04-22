# GIT 오늘 배운거 정리 - 2025.04.22

git bash에서 ctrl + 하면 글자 커짐
* 파일 만들기 touch newfile.txt
* vim
	* :set nu    라인넘버
	* 줄복사 Y, 붙여넣기 p
* 비선형 개발가능. 브랜치. 내가 내꺼 하면 된다
* Github vs Gitlab vs Bitbucket
	* Gitlab : 회사내에 설치 가능
	* Bitbucket : 일정관리 등이랑 연동해서 쓸때
* 레포생성시 MIT License (완전 자유롭게 사용가능한 라이센스)

```bash
# 현재 설정 확인
git config --list
# 잘못된 설정 수정
vi ~/.gitconfig

# 새 설정 등록
git config --global user.name “{username}”
$ git config --global user.email “{emailaddr}”
$ git config --global core.editor “vim”
$ git config --global core.pager “cat”

# 생성된 저장소 받기
git clone https://github.com/mahomi/test-repo.git

# 변경된(커밋할) 파일 확인
git status
git status -uall # 폴더명만 보이는 경우, -uall(untracked all) 옵션을 쓰면 폴더안 파일명까지 나옴

# 커밋할 대상 목록에 추가 (스테이징)
git add main.py
git commit
# 커밋 메시지는 첫줄제목, 엔터두번치고 상세내용입력 가능. (엔터한번치면 그것도 제목으로 인식함)
git push origin main  # origin원격저장소의 main브랜치에 push

# 로그인이 안되는 경우,
# 맥:Keychain Access, 윈도우즈:보완관리자(크리덴셜매니저) 에서 기존 정보 지우면 다시 로그인 요구함

```

## github에 자기 소개 넣기
1. github애서 레포생성에서 레포명을 본인 유저 이름과 동일하게 해고 public으로 하고 add a README file 체크하고 생성을 한다
2. https://rahuldkjain.github.io/gh-profile-readme-generator/
3. 2에서 만든걸 copy하고, github에서 README.md에서 edit누르고  붙여넣는다.

## git ignore
```bash
*.java
pw.*
secrets/**
```

https://www.toptal.com/developers/gitignore/
https://www.toptal.com/developers/gitignore/api/macos,windows,python,vim,visualstudiocode,jupyternotebooks,flask

아래 세가지는 필수적으로  고려할것
* Conventional Commit
* gitingnore
* README.md
## .ipynb
파비콘(오른쪽 상단 메뉴 버튼)에 Feature preview > Rich Jupyter Notebook Diffs

## pre-commit
* pep 8 파이썬 코딩 스타일가이드
	* https://peps.python.org/pep-0008/

## branch
```bash
git branch # local 브랜치 목록 조최
git branch -r # rmote 브랜치 목록 조회
git branch -a # local & remote 브랜치 목록 조회

# 번외
git remote # remote 목록
git remote -v # remote 목록 (주소 표시)
git remote --help
git remote add google https://www.google.com/

git branch 브랜치명  # 브랜치 생성
git switch 브랜치명  # 브랜치 스위치  (checkout -> switch 바뀜)
# 여담. checkout이 switch와 restore로 분리됨

git switch main
git merge fizz  # fizz -> main 병합
git branch -D fizz  # 브랜치 삭제


