# 어떻게 최신 버전의 과제를 적용하나? How apply the latest version of assignment?

과제를 진행하다보면 과제에 변경이 발생하는 경우가 있고, 이를 자신의 저장소(repository)에 저장해야 하는 일이 생깁니다. 이번 매뉴얼에서는 최신 저장소로부터 merge하는 법을 다룹니다.

During an assignment, some modifications on assignment can be occurred and you will apply this to your own repository. In this manual, we will cover how to merge the latest source code to your repository.

1. Setting upstream repository

여러분은 과제를 하기 위해서 조교가 작성한 저장소에서 fork를 진행했을텐데요, 이때 조교가 작성한 저장소를 upstream이라고 부릅니다. (왜 upstream이냐가 궁금하시다면: https://stackoverflow.com/questions/2739376/definition-of-downstream-and-upstream)

You would forked from TA's repository for assignment. We call this TA's repository to "upstream". (Why is it upstream? See this: https://stackoverflow.com/questions/2739376/definition-of-downstream-and-upstream

즉, 현재의 저장소에서 upstream을 정해줘야 하는데요, 다음과 같은 과정을 진행하면 됩니다.

```sh
$ cd ~/working-directory # 현재 작업 중인 디렉터리로 이동 (즉, clone 받아온 곳) Move to your working repository (i.e. cloned repository)
$ git remote -v # upstream과 origin이 설정되어 있나요? origin만 설정이 되어있어야 합니다. Is upstream and origin is configured? Only origin setup should be here.
$ git remote add upstream https://repository_your_TA_wrote.com
```

upstream을 잘 세팅했다면 아래와 같이 나와야합니다.

```sh
$ git remote -v
origin	https://jafffy@bitbucket.org/aeislab/mysh2.git (fetch) # 자신의 repository. Your own repository.
origin	https://jafffy@bitbucket.org/aeislab/mysh2.git (push)
upstream	https://somewhereremote.git (fetch) # Upstream repository.
upstream	https://somewhereremote.git (push)
```

2. Apply all patches you missed

만약 위와 같이 나온다면, merge를 해봅시다.
If you've seen like above output, let's try merging.

```sh
git pull upstream master
```

이렇게 하면 바뀐 부분이 자신의 저장소에도 적용됩니다. 참 쉽죠?
That's it. Easy?

3. Solving merge conflict

TBD
