# SSUMC 7th GitHub Guide Session

## Basic Skills

### Add

```zsh
git add "file name"
```

- "file name"의 파일을 추적 및 Staged로 전환하는 명령어

```zsh
git add .
```

- 작업 중인 모든 파일을 추가 및 Staged로 전환하는 명령어

### Commit

```zsh
git commit -m "Commit Message"

git commit
```

`git commit`을 CLI에 입력하고 나면, vi 편집기를 사용한 편집모드에 들어가게 된다.

### Log

```zsh
git log
```

과거 버전을 확인할 수 있습니다.

### Branch

```zsh
git branch
```

로컬에서 사용 중인 브랜치를 확인하는 명령어

```zsh
git branch --remote
```

원격 레포지토리에서 사용 중인 브랜치를 확인하는 명령어

```zsh
git branch "New Branch Name"
```

"New Branch Name"이라는 이름의 브랜치 개설하는 명령어

### Checkout

```zsh
git checkout "Branch Name"
```

- "Branch Name"의 브랜치로 이동하는 명령어

```zsh
git checkout -b "New Branch Name"
```

- 새로운 브랜치 "New Branch Name"으로 개설하면서 이동하는 명령어

### Remote

```zsh
git remote --v
```

`.git` 파일이 있는 디렉터리가 어떤 원격 레포지토리에 연결되어있는지 확인하는 명령어

### Push

```zsh
git push origin
```

`origin` 원격 레포지토리로 업로드

### Pull

```zsh
git pull
```

현재 작업 중인 브랜치에서 원격 브랜치의 버전이 더 높을 때, 변경사항을 원격에서 로컬로 가져오는 명령어

### Merge

> 개발자가 "Branch A"에서 작업 중이고, "Branch B"의 변경사항을 병합한다고 가정.

```zsh
git merge "Branch B"
```

"Branch B"의 변경사항을 병합하는 명령어

### Pull Request

> Pull Request는 git의 기능이 아니고, GitHub의 기능입니다. \
> D 브랜치의 작업사항을 C 브랜치에 병합을 하고 싶은 상황에서, 팀원들과 변경사항을 공유해야 하는 시나리오가 빈번합니다. \
> `develop` 브랜치에 개발자 개별 작업 브랜치의 변경사항을 병합해야 하는 상황을 앞으로 개발하면서 많이 마주하게 될 것 입니다.

```zsh
git checkout D

git push origin
```

- GitHub Pull Request에서 PR을 개설합니다.
- C 브랜치에 병합합니다. 이 때 병합은 원격 레포지토리의 C 브랜치(origin/c)에 병합이 되어 있습니다.
- 변경된 origin/c 브랜치의 변경 사항을 로컬로 `pull` 받아옵니다.

```zsh
git checkout C

git pull origin
```

## Advanced Skills

### Delete Push

```zsh
git push -d "Remote Name" "Branch Name"
```

원격에 브랜치를 푸시가 되어있는 상황에서, 푸시를 제거하고 싶을 때 수행하는 명령어입니다.

### Fetch

`pull`과 `fetch`의 가장 큰 차이점은 원격의 사항들을 가져와서 로컬에 자동으로 적용한다는 점 입니다.
1. `git fetch` 명령어를 실행하면 레포지토리에 있는 변경사항들을 `origin/branch`으로 가져옵니다.
2. `origin/branch`에 가져온 변경사항들을 `branch`에 적용합니다.

즉 정리하자면, `git pull`로 수행되는 동작을 `git fetch`와 `git merge`로 두 단계를 거쳐서 진행합니다.

그렇다면 해당 작업을 왜 사용하는가?

- 더욱 세부적으로 원격에 있는 변경사항을 적용할 수 있습니다.
- 다른 로컬 브랜치에 번경사항을 적용할 수 있습니다.
  - 예를 들어 `A`라는 브랜치로 원격에 있는 `origin/A`의 변경사항을 적용할 수 있는 상황입니다.
  - 여기서 `B`라는 브랜치에도 `origin/A`를 적용할 수 있습니다.

즉, 더욱 세부적으로 작업할 수 있습니다.

```zsh
git fetch origin
```

```zsh
git merge origin/"fetched branch name"
```

### Stash (임시저장)

> `git stash` 명령어는 현재 작업하던 브랜치에서 다른 브랜치로 전환하는데, 변경사항들을 임시저장하고 넘어가려고 할 때 사용합니다.

```zsh
git stash
```

작업 중인 항목들을 임시저장합니다.

```zsh
git stash push -m "임시저장 타이틀"
```

작업 중인 항목들을 임시저장하는데, 임시저장 타이틀을 지정할 수 있습니다.

```zsh
git stash list
```

임시저장된 변경사항들의 리스트를 보여줍니다.

```zsh
git stash apply stash@{항목번호}
```

임시저장된 항목 중 하나를 선택하여 저장합니다.

### Amend

> `git amend` 명령어는 가장 최근의 커밋 메시지를 수정합니다.

```zsh
git commit --amend
```

가장 최근 커밋 메시지를 수정하는 vi 모드로 진입합니다.

```zsh
git commit --amend --no-edit
```

커밋 메시지 수정 없이, 현재 stage한 항목을 이전 커밋에 넣습니다.

### HEAD

HEAD의 개념
1. HEAD는 일종의 포인터입니다.
2. 터미널에서 현재 상태로 보여지는 값을 HEAD라고 합니다.

### Checkout into Hash

```zsh
git commit checkout "commit hash"
```

과거 버전으로 돌아갑니다.

### Merge Conflict Resolve Editor & GUI Tools

- [GitKraken](https://www.gitkraken.com/)
- VSCode Extensions
  - [GitLens](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens)
  - [GitHub Pull Requests](https://marketplace.visualstudio.com/items?itemName=GitHub.vscode-pull-request-github)

### PR 병합 간 충돌을 줄일 수 있는 팁

> develop 브랜치로 내가 작업 중인 feat/#7 브랜치를 병합하려고 가정을 해봅시다.

`feat/#7` 브랜치를 원격으로 업로드 하기 전에 가장 최신의 `develop` 브랜치를 `feat/#7` 브랜치로 병합합니다.

```zsh
git checkout feat/#7

git merge develop
```

이렇게 했을 때의 이점이 무엇이냐?

- 로컬에서 미리 충돌을 잡고 원격으로 업로드 하기 때문에, 충돌이 발생한다는 불필요한 상황을 미리 해결할 수 있음.
- GitHub에서 웹브라우저에서 충돌을 잡을 수 있는 도구도 있지만, 로컬에서 사용할 수 있는 도구가 훨씬 더 강력해서 개발자의 피로도를 줄일 수 있음.

### Cherry Pick

과거의 커밋들을 현재 작업 중인 브랜치에 비선형적으로 적용할 수 있다.

```zsh
git cherry-pick "커밋해시"
```

### Tag

오픈소스로 사용할 수 있는 레포지토리의 버전을 관리할 수 있습니다. \
태그는 일종의 브랜치와 같이 사용할 수 있습니다. \
`checkout` 명령어도 사용가능합니다.

```zsh
git tag x.x.x
```

```zsh
git push origin x.x.x
```

```zsh
git push -d origin x.x.x
```