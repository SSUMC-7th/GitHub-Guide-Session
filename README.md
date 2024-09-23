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

### Branch

```zsh
git branch
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
