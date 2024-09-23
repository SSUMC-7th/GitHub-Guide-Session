# SSUMC 7th GitHub Guide Session

## Basic Skills

### Add

```zsh
git add "file name"
```

- "file name"의 파일을 추적 및 Staged로 전환

```zsh
git add .
```

- 작업 중인 모든 파일을 추가 및 Staged로 전환

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

원격 레포지토리에서 사용 중인 브랜치를 확인

```zsh
git branch "New Branch Name"
```

"New Branch Name"이라는 이름의 브랜치 개설

### Checkout

```zsh
git checkout "Branch Name"
```

- "Branch Name"의 브랜치로 이동

```zsh
git checkout -b "New Branch Name"
```

- 새로운 브랜치 "New Branch Name"으로 개설하면서 이동

### Remote

```zsh
git remote --v
```

`.git` 파일이 있는 디렉터리가 어떤 원격 레포지토리에 연결되어있는지 확인

### Push

```zsh
git push origin
```

`origin` 원격 레포지토리로 업로드

### Merge

> 개발자가 "Branch A"에서 작업 중이고, "Branch B"의 변경사항을 병합한다고 가정.

```zsh
git merge "Branch B"
```

## Advanced Skills
