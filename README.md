# Git Documentation

## 목차
- [원격 저장소 추가하기](#원격-저장소-추가)
- [원격 저장소 삭제하기](#원격-저장소-삭제)
- [Branch 생성](#branch-생성)
- [Branch 이동](#branch-이동)
- [Branch 생성과 이동](#branch-생성과-이동)
- [Branch 삭제](#branch-삭제)
- [Branch명 변경](#branch명-변경)
- [현재 Branch 확인](#현재-branch-확인)
- [원격 저장소 branch 확인](#원격-저장소-branch-확인)
- [로컬 및 원격 저장소 모든 branch 확인](#로컬-및-원격-저장소-모든-branch-확인)
- [로컬 branch를 원격에 push하기](#로컬-branch를-원격에-push하기)

## 원격 저장소 추가

아래와 같이 현재 연결되어 있는 원격 저장소를 확인 할 수 있다.

```bash
git remote -v
origin git@xxxx (fetch)
origin git@xxx (push)
```

추가하고자 하는 원격 저장소를 **git remote add [단축이름] [저장소주소]** 형식으로 입력하여 추가한 후 **git remote -v** 로 추가 여부를 확인한다.
아래의 예시는 github라는 단축이름으로 github 저장소를 추가하는 모습이다.

```bash
git remote add github  https://github.com/backguru-t/openai.git
git remote -v
github  https://github.com/backguru-t/openai.git (fetch)
github  https://github.com/backguru-t/openai.git (push)
origin  git@xxx (fetch)
origin  git@xxx (push)
```

이제 다음과 같이 두 개 이상의 저장소에 push할 수 있다.
```bash
git push origin master
git push github master
```

## 원격 저장소 삭제
아래의 방식으로 원격 저장소를 삭제할 수 있다. **github** 원격 저장소를 삭제해 보자.

```bash
git remote remove github
```

## Branch 생성
아래와 같이 `git branch` 명령으로 새로운 Branch를 생성할 수 있다.
```bash
git branch <new-branch-name>
```
이 명령은 master Branch에서 *new-branch-name* 이라는 Branch를 생성한다.

## Branch 이동
`git checkout <branch-name>` 명령으로 Branch 이동이 가능하다. 예를 들어, master Branch에서 develop Branch로 이동할 경우에는 다음과 같다.
```bash
git checkout develop
```

## Branch 생성과 이동
새로운 Branch 생성과 이동(checkout)을 한번에 할 수 있다. 예를 들어, develop Branch를 생성하면서 동시에 checkout하는 명령은 다음과 같다.

```bash
git checkout -b develop
```

## Branch 삭제
`git branch -D` 명령으로 제거할 수 있다. 예를 들어, develop Branch 삭제는 다음과 같다.

```bash
git branch -D develop
```

## Branch명 변경
다음과 같이 develop Branch 이름을 mydevelop으로 변경할 수 있다.

```bash
git branch -m develop mydevelop
```

## 현재 Branch 확인
`git branch`  또는 `git branch -v` 명령으로 현재 Branch를 확인할 수 있다.

## 원격 저장소 branch 확인
```bash
git branch -r
```

## 로컬 및 원격 저장소 모든 branch 확인
```bash
git branch -a
```

## 로컬 branch를 원격에 push하기
로컬에 새로 생성한 develop branch를 원격에 push하는 방법은 아래와 같다.
```bash
git push origin develop
```

**Reference**: https://git-scm.com/book/ko/v2


