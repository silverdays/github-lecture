# github-lecture

## 基本概念

### git 和 版本管理工具

版本管理工具的目的是让你或者一个团队，向一个集中的仓库提交文件。这样你可以看到和下载别人的提交记录，也可以当发现错误的时候回退到某个历史版本。还可以自动的把多人的工作合并到一起，或者检测出冲突的地方。

git 是最常见和主流的版本工具。历史上还有 svn。

### GitHub

[GitHub](https://github.com/) 是一个美国公司维护的网站。github 的竞争者还有 [gitlab](https://git.lug.ustc.edu.cn/users/sign_in), [gitee](https://gitee.com/)。 

如果你不想把文件放在它们网站上，也可以非常方便的在自己的服务器上私有部署。

GitHub 上的项目可以选择是公开的或者私有的。除了可以存放自己的代码和文件外，也有非常多人把自己的学习心得放在上面，是个非常好的学习平台。

GitHub 是使用 git 来做版本管理，并使用 markdown（https://www.runoob.com/markdown/md-title.html） 来撰写文本。

## 环境准备

1. 注册github账号： https://github.com/
1. windows 环境可以下载 命令行工具 `git bash for windows`, 或者用 `vscode`，或者 GUI 工具 `GitKraken`. 
1. linux 的用户可以 yum install -y git

可以参考[这篇文章](https://zhuanlan.zhihu.com/p/30044692)

## 基本的 git 命令

常用的 git 命令大概有十几个，你可以参考[这里](https://zhuanlan.zhihu.com/p/25868120)。

你可以结合后续github上的仓库，来学习下如何使用git命令。


```text
git init
git clone
git config
git add
git rm 
git mv 
git commit
git branch
git checkout
git log
git status
git diff
git pull
git push
```

## 基本的 GitHub 操作

### 建立一个Repo

GitHub 上的工程项目称为 `Repository` (不是Project），通常简称为 `repo`。你可以自己建立一个学习用的 repo，比如我现在这个 repo 叫做 `github-lecture`.

### 将这个远程的 Repo clone 到本地的机器上

复制这个HTTPS的地址，然后在你的 `git bash for windows` 里面输入

```shell
git clone 
```

![]https://github.com/silverdays/github-lecture/blob/master/%E6%89%B9%E6%B3%A8%202019-11-13%20134535.png
