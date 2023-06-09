## What is git??

### 스테이지와 커밋 이해하기
* 작업 트리 - 우리의 눈에 보이는 디렉토리로, 실제 작업이 이루어지는 곳을 말합니다.  
* 스테이지 - 만든 파일을 버전에 넣고 싶을 때 파일이 넘어가는 곳입니다.  
* 저장소 - 커밋을 시행했을 때, 스테이지에 있던 파일이 비로소 저장소로 넘어가게 됩니다.  

깃에서 버전을 만드는 것은 위와 같은 순서로 파일이 이동하며 이루어집니다.   

### 파일 커밋하기

```$ git status```

현재 깃의 상태를 확인합니다.
git이 관리하는 디렉토리 내부에서 관리를 할 수 있는 파일을 찾아냅니다.  
한 번도 버전을 관리하지 않으면 untracked files로 표시됩니다.  

```$ git add <file name>```

git의 스테이지에 해당 파일을 추가합니다.  
파일 앞에 new file: 이라는 수식어가 추가됩니다.  
파일 이름 대신 . 를 붙이면 수정한 파일을 전부 스테이지에 올릴 수 있습니다.  

```$ git commit```

git의 저장소에 스테이지에 등록된 파일을 커밋합니다.  
-m : 커밋하면서 메세지를 첨가합니다. -m "message" 의 형태로 사용합니다.  
-am : 스테이지에 올리고 커밋하는 과정을 한 번에 처리합니다. 앞서 커밋을 했던 파일에만 적용됩니다.  

```$ git log```

커밋했던 기록을 출력합니다.  
--no-pager 옵션을 붙이면 로그가 less에서 출력되지 않고, 터미널에서 출력됩니다.  
--stat : 무슨 파일이 커밋되었는지까지 알려줍니다.  
--online : 로그를 한줄로 출력합니다 (메세지 가 잘 출력되므로, 잘 쓰는데 집중합시다)  
--branches : 각 브랜치의 최신 커밋을 한 번에 볼 수 있습니다. 하지만 갈래를 구분하긴 어렵습니다.  
--graph : 각 브랜치의 갈래까지 출력해줍니다.ls-  

```$ git diff```

작업 트리 vs 스테이지의 파일, 혹은 스테이지 vs 저장소의 파일을 비교하여 다른 점을 비교합니다.  
git status를 이용해 파일의 상태를 살펴보면, 'modified'가 출력됩니다.  
이 때 diff를 사용해 어느 부분이 변경되었는지 알 수 있습니다.  
역시나 --no-pager 옵션을 사용해 less 창을 출력하지 않게 할 수 있습니다.  

### tracked vs untracked

한 번이라도 커밋을 한 파일을 trakced 파일, 한 번도 커밋하지 않아 추적할 수 없는 파일을 untracked 파일이라고 합니다.  

```.gitignore```

파일을 생성해 내부에 디렉토리, 파일명, 혹은 확장자를 적어 버전을 관리하지 않을 파일을 지정할 수 있습니다.  
주로 백업 파일, swp파일 (이게 뭐지) 등이 포함됩니다.  

### modified, unmodified, staged

셋은 모두 tracked 된 상태입니다.  
modified : 수정이 감지된 파일입니다.  
unmodified : 수정되지 않은 파일입니다.  
staged : add 되어 스테이지에 올라간 파일입니다. commit으로 저장소에 올리는 게 가능합니다.  

### 파일 되돌리기

```git checkout -- <filename>```

수정한 파일을 되돌리기 위해 사용합니다.  
tracked된 파일만 동작합니다.  

```git reset ```

HEAD <filename>  
스테이지에 올라간 (add를 사용한) 파일을 스테이지에서 내리기 위해 사용합니다.   
HEAD^ <filename>  
커밋까지 실시한 파일을 되돌리기 위해 사용합니다.  
--hard <commit hash>  
해당 커밋 해시를 가진 커밋까지 되돌리고, 그 이후 커밋은 모두 삭제합니다.  

```git revert <hash>```

해당 커밋까지 되돌리지만, 위와 달리 이후의 커밋을 삭제하기 않고 남겨둡니다.  


