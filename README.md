# github-lecture

---

本文阅读大约需要7分钟。

本文术语并不严格，目的是帮助快速理解git、github的操作。

欢迎提交 pr 打卡。

---

## 基本概念

### git 和 版本管理工具

版本管理工具的目的是让你或者一个团队，向一个（集中的）仓库提交文件。这样你可以看到和下载别人的提交记录，也可以当发现错误的时候回退到某个历史版本。还可以自动的把多人的工作合并到一起，或者检测出冲突的地方。

git 是最常见和主流的版本工具。历史上还有 svn。


### GitHub

[GitHub](https://github.com/) 是一个美国公司维护的网站。github 的竞争者还有
[gitlab](https://git.lug.ustc.edu.cn/users/sign_in), [gitee](https://gitee.com/)。 

如果你不想把文件放在它们网站上，也可以非常方便的在自己的服务器上私有部署。

GitHub 上的项目可以选择是公开的或者私有的。除了可以存放自己的代码和文件外，也有非常多人把自己的学习心得放在上面，是个非常好的学习平台。

GitHub 是使用 git 来做版本管理，并使用 [markdown](https://www.runoob.com/markdown/md-title.html) 来撰写文本。

### git 操作有4个相关的概念

- 你笔记本上的windows目录，这个文件还没有被git所管理
- 你笔记本上的git工作区，在你本地已经被git所管理
- 你的GitHub仓库，这个是在远程的
- 别人的GitHub仓库，这个也在远程，你通常会fork到你的仓库慢慢研究

## 环境准备

1. 注册github账号： https://github.com/
1. windows 环境可以下载 命令行工具 `git bash for windows`, 或者用 `vscode`，或者 GUI 工具 `GitKraken`，或者直接[点击链接下载](https://gitforwindows.org/)
1. linux 的用户可以 yum install -y git

准备环境可以参考[这篇文章](https://zhuanlan.zhihu.com/p/30044692)

## 基本的 git 命令

常用的 git 命令大概有十几个，你可以参考[这里](https://zhuanlan.zhihu.com/p/25868120)。

你可以结合后续github上的仓库，来学习下如何使用git命令。


```bash
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

## 基本的 GitHub 操作（在自己的空间里面）

### 建立一个Repo

GitHub 上的工程项目称为 `Repository` (不是Project），通常简称为 `repo`。你可以自己建立一个学习用的 repo，比如我现在这个 repo 叫做 `github-lecture`.

![](https://github.com/silverdays/github-lecture/blob/master/%E6%89%B9%E6%B3%A8%202019-11-13%20150901.png)

### 将这个远程的 Repo clone 到本地的机器上

复制这个HTTPS的地址，（**换成你的空间项目地址**）

![](https://github.com/silverdays/github-lecture/blob/master/%E6%89%B9%E6%B3%A8%202019-11-13%20134535.png)

然后在你的 `git bash for windows` 里面输入

```shell
git clone https://github.com/silverdays/github-lecture.git
```

![](https://github.com/silverdays/github-lecture/blob/master/%E6%89%B9%E6%B3%A8%202019-11-13%20135050.png)

> 通常你不需要在本地新建一个项目目录，clone 的时候会为你建好这个项目目录

### 做一些本地修改，并提交到本地git仓库。

你可以用文本编辑器，对文件做一些修改，然后保存。

下面这个命令```git status```可以看到我们修改了 README.MD 文件，并且新增加了一个文件。（中文的文件名`git bash`显示有些问题，但是是可以正常工作的）

```shell
git status
```

![](https://github.com/silverdays/github-lecture/blob/master/%E6%89%B9%E6%B3%A8%202019-11-13%20140117.png)


用 ```git add``` 把新增加的文件交给git管理。你可以看到未管理的文件是红色，已管理的文件是绿色。

```shell
git add 批注\ 2019-11-13\ 135944.png
```

然后用 ```git commit -a ``` 提交给你本地的仓库。但这个时候**还没有**提交到**远程仓库**中。

### 把本地修改推送到远程仓库

你需要配置一些权限，来保证你可以推送到远程的仓库（否则别人可以随便删除你的文件了）

参考[这篇文章](https://blog.csdn.net/u013778905/article/details/83501204)来配置权限。

GitHub多账户问题可以参考[这里](https://blog.csdn.net/Candy_mi/article/details/86157288)

```shell
git push
```

以下提示说明有其他人也有更改，和你本地有冲突。

```text
 ! [rejected]        master -> master (fetch first)
error: failed to push some refs to 'https://github.com/silverdays/github-lecture.git'
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. This is usually caused by another repository pushing
hint: to the same ref. You may want to first integrate the remote changes
hint: (e.g., 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
```

那你可以先```git pull```完成合并后，再运行命令提交```git push```。

由于多人开发的时候，冲突非常常见，参考这里查看关于如何[解决冲突合并](https://blog.csdn.net/qq_24735877/article/details/80847372).

如果```git push```成功，你可以打开浏览器，查看GitHub上结果是否已经更新。

## 学习别人的仓库，并给他提交改动或者问题

我们除了可以使用自己的github仓库作为一个远程的备份外，GitHub 的一个很大的作用是学习别人的仓库，并给他提交一些更新或者问题。

![](https://github.com/silverdays/github-lecture/blob/master/%E6%89%B9%E6%B3%A8%202019-11-13%20143731.png)

### fork 别人的仓库

点击 fork ，把别人的仓库拷贝一份到自己的仓库里面，这样你就可以默默的学习了。比如你可以 fork 本项目，然后做些修改再提交给我（见后）。

比如我这里 fork 了一个很不错的[项目](https://github.com/vesoft-inc/nebula), GitHub 提示我它的来源是 vesoft-inc/nebula.

![](https://github.com/silverdays/github-lecture/blob/master/%E6%89%B9%E6%B3%A8%202019-11-13%20151355.png)

### 点击 star

点 star 相当于淘宝上的收藏，你可以下次方便找到这个项目。

![](https://github.com/silverdays/github-lecture/blob/master/%E6%89%B9%E6%B3%A8%202019-11-13%20144042.png)

star 也是你善意的体现，是在 GitHub 上的良好互动。

![](https://github.com/silverdays/github-lecture/blob/master/%E6%89%B9%E6%B3%A8%202019-11-13%20151725.png)

### 点 watch，选择 Releases only

Releases only 表示当有版本发布的时候会邮件通知你。 watching 表示有风吹草动都通知你（如果你选择 watching , 那邮箱需要分类邮件通知，不然会爆炸的）

![](https://github.com/silverdays/github-lecture/blob/master/%E6%89%B9%E6%B3%A8%202019-11-13%20144227.png)

### 给他提交 issue

当你有任何疑问的时候，可以给他提交一个issue。维护良好的项目会有人来帮忙回答问题。不要害羞，GitHub上的作者都是非常热情的，这也是你学习和交流的好机会。使用中文或者英文都是可以的。

![](https://github.com/silverdays/github-lecture/blob/master/%E6%89%B9%E6%B3%A8%202019-11-13%20144755.png)

### 给他提交一些代码或者更新 (pull request)

你也许会发现他的代码或者文档里面有些错误（比如这篇文档里面，我有意遗漏了一些错误），那么你就可以给他提交一个 pull request (pr)，帮他 fix 这些错误。如果他审核同意审核，就能合并你的pr到他的仓库中。

你可以参考[这篇文章](https://www.jianshu.com/p/b365c743ec8d)来提交pr。

如果你阅读了本文，你可以试试提交一个pr在本文**打卡**，来验证一下你已经会使用github提交PR了。例如

```text
2019/11/13 silverdays initial pos
// 来这里添加一条你的打卡记录吧
// TTTTerry 2019/12/03
// Johnson 2019/12/03
```

这是一个测试和学习的项目，欢迎你来试验一下提交PR。如果我发现你的PR错误，我会帮你一起指出的。

# 如果你想尝试完整一些的企业级开源项目

欢迎你 star 和 fork [这个项目](https://github.com/vesoft-inc/nebula)，即使你今天还不是很明白，也能大体体会下企业级的开源是如何工作的。

# 最后，推荐几个不错的学习地址

欢迎你也为本文添加一些学习心得和学习地址，这样可以造福后人。

- [github自带教程](https://github.com/silverdays/github-slideshow)
- [知乎上不错的总结](https://www.zhihu.com/question/21669554/answer/890230959)

## 踩坑记录

如果你踩了什么坑，欢迎记录在这里。
111
