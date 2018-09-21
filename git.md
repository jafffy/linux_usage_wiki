# Git
Git 은 Distributed Version Control System 입니다.

## Tutorial
git 의 자세한 명령어들을 설명하기 이전에 기본적인 git 의 단계에 대해서 알아보도록 합시다. 
git 은 일반적으로 코드를 생성하는 단계를 포함해서 4단계로 구성됩니다.

__코드작성__    
git repo(repository) 에 아무 파일이나 만들어서 저장합니다. 그럼 다음과 같은 
git 의 상태가 출력됩니다.
```bash
$ git status
On branch master

Untracked files:
    (use "git add <file>..." to include in what will be committed)
        something.file
```
이와 같은 상황을 `untracked` 라고 부르며 이 경우 git 은 저 파일이 
새로운 파일인 사실만 알 뿐 저 파일의 내용이 변경되었는지 알 수 없습니다. 
그래서 우리는 이 파일의 변경여부를 확인하기 위해 다음 단계로 넘어갑니다.

__Stage__    
이 단계로 넘어오기 위해선 해당 파일을 다음과 같은 명령어로 stage 에 등록해야합니다.
```bash
$ git add something.file
```

이렇게 명령어를 등록하고 나면 다음과 같이 파일을 추적할 수 있게 됩니다.
```bash
$ git status
On branch master

Changes to be committed:
    new file: something.file
```

만약 여기서 이 파일의 내용을 변경한다면 이제 git 은 그 사실을 알 수 있고 다음과 같은 
상태를 남깁니다.
```bash
$ git status
On branch master

Changes not staged for commit:
    (use "git add <file>..." to update what will be committed)
    modified: something.file
```

그런데 이 경우 아까 이 파일을 `git add` 했음에도 불구하고 `git add` 를 하라는 메세지가 
출력됩니다. 사실 이 stage area 는 `untraked` 뿐만 아니라 `modified` 파일들도 포함하지 않습니다.
이 이유는 stage area 의 존재 이유때문입니다. 기본적으로 stage area 는 commit 의 준비단계입니다. 
즉 이 단계에선 개발자가 어떤 변경이든 로그를 남기지 않고 작업할 수 있습니다. 만약 
이러한 단계가 없이 변경사항이 있을때마다 소위 `version` 을 만드는 commit 진행하게 된다면 
엄청난 오버헤드가 발생할 것입니다. 

그래서 아아... 뭔가 다시(설명 필요) 

__Commit__    
이 단계까지 왔으면 git 을 거진 다 이용하게 되는 셈입니다. 
이전 버전과 어떻게 다른지 어떠한 점이 고쳐졌는지에 대한 로그와 
변경사항들을 하나의 `version` 으로 만듭니다.

```bash
$ git commit
or
$ git commit -m "Added something.file"
```

첫 번째 commit 의 경우 git 에서 기본적으로 설정한 editor 로 commit log 를 남깁니다.
두 번째의 경우 editor 의 도움없이 바로 일정 단어 수만큼의 메세지를 포함하여 commit 
log 를 남깁니다.

__Push__    
대부분의 경우가 그러겠지만 해당 repo 가 remote repo 에서 가져온 것이라면 
나의 log 을 여러 사람들에게 알리기 위해 혹은 remote repo 에 백업을 해놓을 목적으로 
내 commit log 를 `push` 합니다. 

```bash
$ git push origin master
# git push <remote name> <branch name>
```


## Command (in detail)
__git init__    
로컬 컴퓨터에 있는 디렉토리를 git 디렉토리로 변환합니다. (정확히, 디렉토리 안에 
git 관련 파일들을 생성하고 git 이 디렉토리를 추적할 수 있게합니다.)
```bash
$ mkdir mydir
$ cd mydir
$ git init
```

__git config__    
`.git/config` 파일에 있는 설정들을 수정하거나 새로운 속성을 추가합니다. 디렉토리마다 
설정할 수 있으며 또는 `--global` 옵션을 사용하여 일반적인 설정으로 정의할 수 있습니다. 
주로 아래와 같은 예로 많이 사용됩니다.
```bash
# git 관련 ediotr 를 vi 로 설정 
$ git config --global editor vi

# commit log 를 남길 user 설정
$ git config user.name "Morty Smith"
$ git config user.email "mortys@rickandmorty.com"
```

__git clone__    
`ssh` 혹은 `http(s)` 로 된 git repo 를 로컬 컴퓨터로 가져옵니다.
```bash
$ git clone http://something.com/something.git
or
$ git clone ssh://something@something:something.git
```

__git add__    
디렉토리/파일 들을 stage area 에 등록합니다.

```bash
# 일반적인 경우
$ git add something.c

# 파일 내용을 확인하면서 stage 하고 싶은 경우
$ git add -p something.c # 새로운 파일은 사용하지 못 함
```

__git commit__    
staged filed 들을 commit 합니다.
```bash
$ git commit
$ git commit -m "short case"
```

__git status__    
git repo 내부 file 들의 변경사항들을 확인합니다.
```bash
$ git status
```

__git log__    
Commit log 를 확인합니다.
```bash
# Normal
$ git log

# Log trace 확인가능
$ git log --graph
```

__git push__    
내 로컬의 commit log 들을 지정된 remote repo 로 보냅니다.
```bash
# 원형
$ git push <remote name> <remote branch name>

# 일반적인 경우
$ git push origin master

```

__git pull__    
지정된 remote repo 의 변경내용을 가져옵니다.
```bash
# 원형
$ git pull <remote name> <remote branch name>

# 일반적인 경우
$ git pull origin master
```

__git branch__    
새로운 브랜치를 생성하거나 수정하거나 볼 수 있습니다.
```bash
# 새로운 branch 생성
$ git branch <new branch name>

# 현재 branch 정보 확인
$ git branch -v

# 해당 branch 삭제
$ git branch -d <del branch name>
```

__git retmoe__    
```bash
$ git remote -v
```


__git checkout__    
```bash
$ git checkout <branch name>

$ git checkout -- something.c
```

__git rebase(과연 이것까지...)__


## GUI
* [Sourcetree](https://www.sourcetreeapp.com/)
* [Github Desktop](https://desktop.github.com/)




## Reference
* [git-scm](https://git-scm.com/)
* [Git staging area 의 이점](https://blog.npcode.com/2012/10/23/git%EC%9D%98-staging-area%EB%8A%94-%EC%96%B4%EB%96%A4-%EC%A0%90%EC%9D%B4-%EC%9C%A0%EC%9A%A9%ED%95%9C%EA%B0%80/)
