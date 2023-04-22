## What is branch?

### << 브랜치란?

각종 버전들의 분기를 만들거나, 각종 버전을 병합하는 기능을 가진 도구입니다.  
브랜치는 커밋을 가리키는 포인터와 같으며, 사용자의 최신 커밋은 master 브랜치에 저장됩니다.  
*(master)의 이름은 달라질 수 있음*

### << 브랜치 만들기

```bash
$ git branch
```

현재 저장소에서 만들어진 branch를 확인합니다.  
\* 표시는 현재 작업하고 있는 branch입니다.  

### << 브랜치 사이 이동하기

```bash
$ git checkout <branch-name>
```
  
해당 브랜치로 이동합니다.  

### << 새 브랜치에서 커밋하기

```bash
$ git log
```

--oneline, --branches, --graph -> [what-is-git](https://keplerisgone.github.io/posts/What_is_Git/)을 참조하세요.  
<branchname1..branchname2> : branchname1에는 없고 branchname2에만 있는 커밋을 보여줍니다.  

### << 브랜치 병합하기

```bash
$ git merge <branch-name>
```

현재 브랜치와 해당 브랜치를 병합합니다.  
두 브랜치에서 같은 문서를 수정한 후 병합하면 "줄 단위"로 자동으로 병합합니다.  
따라서 같은 줄을 동시에 수정했다면 충돌이 발생하게 됩니다.  
이 때는 알아서 git이 파일을 수정해주는데, 이를 따라서 수정하면 충돌을 막을 수 있습니다.  

### << 브랜치 삭제하기
 
```bash
git branch -d <branch-name>
```

해당 브랜치를 삭제합니다. 완전히 저장소에서 브랜치를 없애는 것은 아니고, 감추는 것에 가깝습니다.  
해당 브랜치와 동일한 이름의 브랜치를 나중에 다시 생성하면, 다시 그대로 나타납니다.  

### << 브랜치 넘나들기

```bash
git reset <hash>
```

해당 해시로 현재 브랜치를 되돌립니다, 여기서 다른 브랜치의 해시를 이용해 돌릴 수도 있습니다.  

```bash
git stash
```

파일을 git에게 숨김니다. 정확히는 파일을 수정한 내용을 따로 저장하는 것이며, 해당 파일을 커밋하지 않고 다른 파일을 커밋할 수 있습니다.   

```bash
git stash pop
```

stash 에서 가장 최근 파일을 불러옵니다.   
pop 대신...   
apply : 수정 내용을 그대로 남겨둡니다.   
drop : stash 목록을 삭제한다.   