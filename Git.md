# Git 使用笔记

## 基本操作

```bash
git add file1.txt
git add file2.txt file3.txt

git commit -m "add 3 files."

用户名和邮箱:
git config --gloabal user.name "bixingjian"

查看:
git config --global user.name
```

## 版本管理

> 查看版本和内容

```bash
#查看工作区,暂存区状态
git status

#查看修改了什么内容
git diff readme.txt

#由近到远提交的日志
git log
#如果嫌输出信息太多，看得眼花缭乱的
git log --pretty=oneline
```

> 当前 commit->之前的 commit (没有 push 到远程仓库之前)

```bash
#HEAD表示当前版本，也就是最新的提交1094adb
#上一个版本是HEAD^
#上上一个版本是HEAD^^
#往上100个版本是HEAD~100。
git reset --hard HEAD^
#退回去之后还可以回来
git reset --hard 1094a#不用输完整个的id
#有时候要回来的id不好找到, 使用日志查看历史命令 决定回到哪个版本
git reflog
```

<img src="https://i.loli.net/2021/02/18/yf9YpjkEFoOs7cG.png" alt="image-20210217182337462" style="zoom:80%;" />

> 暂存区->工作区

```bash
git reset HEAD readme.txt #HEAD代表最新的把呢不能
```

> 修改的本地文件->修改之前的本地文件

```bash
#撤销文件修改
git checkout -- readme.txt#注意readme和--之间有空格
```

命令 `git checkout -- readme.txt`意思就是，把 `readme.txt`文件在工作区的修改全部撤销，这里有两种情况：

一种是 `readme.txt`自修改后还没有被放到暂存区，现在，工作区的修改就没了；

一种是 `readme.txt`已经添加到暂存区后，又作了修改，现在，撤销修改就回到添加到暂存区后的状态。

```bash
#修改之前(readme.txt文件)
the first comment.

#修改之后
the first comment.
the second comment.

#运行git checkout -- readme.txt
the first comment.
```

> 删除文件

删除工作区文件, 工作区和版本库就不一样了.

```bash
#删除本地文件
手动删除 or 命令行rm删除

#在版本库中将文件删除
#先手动删除文件，然后使用git rm <file>和git add<file>效果是一样的。
git rm test.txt
git add test.txt #"add"删除操作

#将删除操作commit
git commit -m "delete test.txt删除文件"
```

## 远程仓库

> 添加远程仓库

```bash
git remote add origin https://github.com/bixingjian19/sdfgsdg.git
```

添加后，远程库的名字就是 `origin`，这是 Git 默认的叫法

> 更改远程仓库

```bash
origin>
```

> push 到远程仓库

```bash
#第一次push到远程
git push -u origin main

#之后push
git push
#or
git push origin main
```

当前分支 `master`推送到远程

由于远程库是空的，我们第一次推送 `master`分支时，加上了 `-u`参数，Git 不但会把本地的 `master`分支内容推送的远程新的 `master`分支，还会把本地的 `master`分支和远程的 `master`分支关联起来，在以后的推送或者拉取时就可以简化命令。

**-git push -u origin master 中 u 参数的和含义**

https://stackoverflow.com/questions/5561295/what-does-git-push-u-mean

"Upstream" would refer to the main repo that other people will be pulling from, e.g. your GitHub repo. The -u option automatically sets that upstream for you, linking your repo to a central one. That way, in the future, Git "knows" where you want to push to and where you want to pull from, so you can use `git pull` or `git push` without arguments. A little bit down, [this article](http://mislav.uniqpath.com/2010/07/git-tips/) explains and demonstrates this concept.

**git push 和 git push origin master 的区别**

https://stackoverflow.com/questions/29858663/what-is-the-difference-between-git-push-and-git-push-origin-master/29858688

`git push` assumes that you already have a [remote repository](http://git-scm.com/book/en/v2/Git-Basics-Working-with-Remotes) defined for that branch. In this case, the default remote `origin` is used.

`git push origin master` indicates that you are pushing to a _specific_ remote, in this case, `origin`.

This would only matter if you created multiple remote repositories in your code base. If you're only committing to one remote repository (in this case, _just_ your GitHub repository), then there isn't any difference between the two.

## 分支管理

### 分支基本操作

> 创建+切换分支

```bash
#switch比较好 下面两条作用一样
git switch -c dev
git checkout -b dev

#创建分支+切换分支
git branch dev
```

> 查看当前已有的分支

```bash
git branch
```

> 切换分支

```bash
git switch master
git checkout master`
```

> 合并分支

```bash
#将dev分支的结果合并到master上(在master分支中操作)
git merge dev
```

merge 将指定分支合并到当前分支

> 删除分支

```bash
git branch -d dev
```

> 在远程仓库添加新分支

解决报错: **The current branch dev has no upstream branch**

```bash
git push --set-upstream origin dev
```

不然远程仓库不显示在本地创建的分支

### 分支冲突

> 分支冲突

在 dev 分支上修改了文件

在 master 分支上也修改文件

无法快速 merge, 需要手动更改文件再合并

<img src="https://i.loli.net/2021/02/18/8PKO91rlhLtEguR.png" alt="image-20210217222615426" style="zoom: 67%;" />

<img src="https://i.loli.net/2021/02/18/clDWCqQaMO7spjv.png" alt="image-20210217222459485" style="zoom: 67%;" />

> 查看分支合并情况

```bash
git log --graph --pretty=oneline --abbrev-commit
```

### 合并策略

> 快速合并

默认都是快速合并， 直接将 master 分支指向 dev 分支

如果当前的分支和另一个分支没有内容上的差异，就是说当前分支的每一个提交(commit)都已经存在另一个分支里了

<img src="https://i.loli.net/2021/02/18/e2NVwSmbCDjIEHo.png" alt="image-20210217224514371" style="zoom: 67%;" />

> 非快速合并

使用快速合并： 删除分支后， 分支信息就没了

使用非快速合并：在 merge 时生成一个 commit， 在分支历史上就可以看出分支信 “开叉”，可以让我们的提交历史更加的清晰！

```
#非快速merge在merge的同时进行一次提交
git merge --no-ff -m "merge with no-ff" dev
```

<img src="https://i.loli.net/2021/02/18/yBLGVHx3zkR4iP6.png" alt="image-20210217224800443" style="zoom: 67%;" />

> 快速合并和非快速合并的区别

https://blog.csdn.net/andyzhaojianhui/article/details/78072143

> 分支策略

master 是主分支 保持稳定

干活在 dev 上， 到一定版本 1.0， 再合并到主分支 master

不同员工在自己分支， 不时想 dev 合并

<img src="https://i.loli.net/2021/02/18/wJ6E7saGptxCkQv.png" alt="image-20210217225104751" style="zoom:67%;" />

### bug 分支和 feature 分支

> 暂存当前分支

```bash
git stash
```

> 查看 stash 列表

```bash
git stash list
```

> 恢复 stash

```bash
git stash pop
git stash apply stash@{0}
```

> 新建分支处理 bug

- 我们当前在 dev 上, master 分支有一个 bug 需要我们处理
- 我们 dev 还 commit, 所以先 stash 保存当前状态, 然后切换到 master
- 新建 issue-101 处理 bug, 处理完 bug 之后 merge 到 master 分支

  - ```bash
    git merge --no-ff -m "merged bug fix 101" issue-101
    ```

    **注意: 这里不能使用快速向前合并 ff, 原因: **

    **快速向前合并使用条件是当前的分支和另一个分支没有内容上的差异，就是说当前分支的每一个提交 (commit)都已经存在另一个分支里了**

    **而我们这个提交解决了 mater 的一个 bug, master 合并前后内容不一样了, 不能使用 ff**

- 删除 issue-101 分支, stash pop 返回 dev 分支

因为 dev 是从 master 拉出来的, 所以 master 上这个 bug 在 dev 上也有, 使用 cherry-pick 将 bug 上解决 bug 的修改"复制"到 dev 分支上

简单花了一个流程图, 如下:

<img src="https://i.loli.net/2021/02/18/Nodl7McngPvVfIe.png" alt="git-bug分支" style="zoom: 50%;" />

> feature 分支

如果要丢弃一个没有被合并过的分支，可以通过 `git branch -D <name>`强行删除。

### 多人协作

当你从远程仓库克隆时，实际上 Git 自动把本地的 `master`分支和远程的 `master`分支对应起来了，并且，远程仓库的默认名称是 `origin`

> 查看远程仓库信息(verbose 模式)

```bash
git remote -v
```

> 推送分支

将本地(master)推送到远程(origin)

```bash
git push origin master

git push origin master
```

**但是，并不是一定要把本地分支往远程推送，那么，哪些分支需要推送，哪些不需要呢？**

- `master`分支是主分支，因此要时刻与远程同步；
- `dev`分支是开发分支，团队所有成员都需要在上面工作，所以也需要与远程同步；
- bug 分支只用于在本地修复 bug，就没必要推到远程了，除非老板要看看你每周到底修复了几个 bug；
- feature 分支是否推到远程，取决于你是否和你的小伙伴合作在上面开发

> fetch 分支(pull)

**将远程最新的 dev pull 下来与本地的 dev 比较并解决冲突**

多人协作的工作模式通常是这样：

1. 首先，可以试图用 `git push origin <branch-name>`推送自己的修改；
2. 如果推送失败，则因为远程分支比你的本地更加新，需要先用 `git pull`把最新的提交从 `origin/dev`抓下来，然后，在本地合并；
3. 如果合并有冲突，则解决冲突，并在本地提交；
4. 没有冲突或者解决掉冲突后，再用 `git push origin <branch-name>`推送就能成功！

如果 `git pull`提示 `no tracking information`，则说明本地分支和远程分支的链接关系没有创建，用命令 `git branch --set-upstream-to <branch-name> origin/<branch-name>`。

## github

### 使用

- 创建仓库
- 本地克隆 就行了
