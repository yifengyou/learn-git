# Git简介

Git(读音为/gɪt/。)是一个开源的分布式版本控制系统，可以有效.高速的处理从很小到非常大的项目版本管理。
Git 是 Linus Torvalds 为了帮助管理 Linux 内核开发而开发的一个开放源码的版本控制软件。

Torvalds 开始着手开发 Git 是为了作为一种过渡方案来替代 BitKeeper，后者之前一直是 Linux 内核开发人员在全球使用的主要源代码工具。开放源码社区中的有些人觉得BitKeeper 的许可证并不适合开放源码社区的工作，因此 Torvalds 决定着手研究许可证更为灵活的版本控制系统。尽管最初 Git 的开发是为了辅助 Linux 内核开发的过程，但是我们已经发现在很多其他自由软件项目中也使用了 Git。例如 很多 Freedesktop 的项目迁移到了 Git 上。

# Git安装

Git 的工作需要调用 curl，zlib，openssl，expat，libiconv 等库的代码，所以需要先安装这些依赖工具。

在有 yum 的系统上（比如 Fedora）或者有 apt-get 的系统上（比如 Debian 体系），可以用下面的命令安装：

各 Linux 系统可以很简单多使用其安装包管理工具进行安装：

Debian/Ubuntu Git 安装命令为：

```
$ apt-get install libcurl4-gnutls-dev libexpat1-dev gettext \
  libz-dev libssl-dev

$ apt-get install git-core

$ git --version
git version 2.7.4
```
Centos/RedHat 安装命令为：
```
$ yum install curl-devel expat-devel gettext-devel \
  openssl-devel zlib-devel

$ yum -y install git-core

$ git --version
git version 2.7.4
```

# 特点

分布式相比于集中式的最大区别在于开发者可以提交到本地，每个开发者通过克隆（git clone），
在本地机器上拷贝一个完整的Git仓库。
下图是经典的git开发过程。

![git开发过程](https://github.com/yifengyou/learn-git/raw/master/image/git开发过程.png)

### Git的功能特性：
从一般开发者的角度来看，git有以下功能：
1. 从服务器上克隆完整的Git仓库（包括代码和版本信息）到单机上。
2. 在自己的机器上根据不同的开发目的，创建分支，修改代码。
3. 在单机上自己创建的分支上提交代码。
4. 在单机上合并分支。
5. 把服务器上最新版的代码fetch下来，然后跟自己的主分支合并。
6. 生成补丁（patch），把补丁发送给主开发者。
7. 看主开发者的反馈，如果主开发者发现两个一般开发者之间有冲突（他们之间可以合作解决的冲突），就会要求他们先解决冲突，然后再由其中一个人提交。如果主开发者可以自己解决，或者没有冲突，就通过。
8. 一般开发者之间解决冲突的方法，开发者之间可以使用pull 命令解决冲突，解决完冲突之后再向主开发者提交补丁。

从主开发者的角度（假设主开发者不用开发代码）看，git有以下功能：

1. 查看邮件或者通过其它方式查看一般开发者的提交状态。
2. 打上补丁，解决冲突（可以自己解决，也可以要求开发者之间解决以后再重新提交，如果是开源项目，还要决定哪些补丁有用，哪些不用）。
3. 向公共服务器提交结果，然后通知所有开发人员。

### 优点：
- 适合分布式开发，强调个体。
- 公共服务器压力和数据量都不会太大。
- 速度快.灵活。
- 任意两个开发者之间可以很容易的解决冲突。
- 离线工作。

### 缺点：
- 资料少（起码中文资料很少）。
- 学习周期相对而言比较长。
- 不符合常规思维。
- 代码保密性差，一旦开发者把整个库克隆下来就可以完全公开所有代码和版本信息。



---

# 创建新仓库

创建新文件夹，打开，然后执行

    git init

以创建新的 git 仓库。

---
# 检出仓库

执行如下命令以创建一个本地仓库的克隆版本:

    git clone /path/to/repository

如果是远端服务器上的仓库，你的命令会是这个样子:

    git clone username@host:/path/to/repository

---

#工作流
你的本地仓库由 git 维护的三棵“树”组成。

* 第一个是你的 工作目录，它持有实际文件
* 第二个是 暂存区（Index），它像个缓存区域，临时保存你的改动
* 最后是 HEAD，它指向你最后一次提交的结果。  

![worktree](https://github.com/yifengyou/learn-git/blob/master/image/worktree.png)

---


# 添加和提交

你可以提出更改（把它们添加到暂存区），使用如下命令：

    git add <filename>
    git add *

这是 git 基本工作流程的第一步；使用如下命令以实际提交改动：

    git commit -m "代码提交信息"

现在，你的改动已经提交到了 HEAD，但是还没到你的远端仓库。

---

# 推送改动

你的改动现在已经在本地仓库的 HEAD 中了。执行如下命令以将这些改动提交到远端仓库：

    git push origin master

可以把 master 换成你想要推送的任何分支。

如果你还没有克隆现有仓库，并欲将你的仓库连接到某个远程服务器，你可以使用如下命令添加：

    git remote add origin <server>

如此你就能够将你的改动推送到所添加的服务器上去了。

---

# 分支

分支是用来将特性开发绝缘开来的。在你创建仓库的时候，master 是“默认的”分支。在其他分支上进行开发，完成后再将它们合并到主分支上。

![branchs](https://github.com/yifengyou/learn-git/blob/master/image/branchs.png)

创建一个叫做“feature_x”的分支，并切换过去：

    git checkout -b feature_x

切换回主分支：

    git checkout master

再把新建的分支删掉：

    git branch -d feature_x

除非你将分支推送到远端仓库，不然该分支就是 不为他人所见的：

    git push origin <branch>

---

# 更新与合并

要更新你的本地仓库至最新改动，执行：

    git pull

以在你的工作目录中 获取（fetch） 并 合并（merge） 远端的改动。

要合并其他分支到你的当前分支（例如 master），执行：

    git merge <branch>

在这两种情况下，git 都会尝试去自动合并改动。遗憾的是，这可能并非每次都成功，并可能出现冲突（conflicts）。 这时候就需要你修改这些文件来手动合并这些冲突（conflicts）。改完之后，你需要执行如下命令以将它们标记为合并成功：

    git add <filename>

在合并改动之前，你可以使用如下命令预览差异：

    git diff <source_branch> <target_branch>

---

# 标签

为软件发布创建标签是推荐的。这个概念早已存在，在 SVN 中也有。你可以执行如下命令创建一个叫做 1.0.0 的标签：

    git tag 1.0.0 1b2e1d63ff

1b2e1d63ff 是你想要标记的提交 ID 的前 10 位字符。可以使用下列命令获取提交 ID：

    git log

你也可以使用少一点的提交 ID 前几位，只要它的指向具有唯一性。


---

# log

如果你想了解本地仓库的历史记录，最简单的命令就是使用:

    git log

你可以添加一些参数来修改他的输出，从而得到自己想要的结果。 只看某一个人的提交记录:

    git log --author=bob

一个压缩后的每一条提交记录只占一行的输出:

    git log --pretty=oneline

或者你想通过 ASCII 艺术的树形结构来展示所有的分支, 每个分支都标示了他的名字和标签:

    git log --graph --oneline --decorate --all

看看哪些文件改变了:

    git log --name-status

这些只是你可以使用的参数中很小的一部分。更多的信息，参考：

    git log --help

---

# 替换本地改动

假如你操作失误（当然，这最好永远不要发生），你可以使用如下命令替换掉本地改动：

    git checkout -- <filename>

此命令会使用 HEAD 中的最新内容替换掉你的工作目录中的文件。已添加到暂存区的改动以及新文件都不会受到影响。

假如你想丢弃你在本地的所有改动与提交，可以到服务器上获取最新的版本历史，并将你本地主分支指向它：

    git fetch origin
    git reset --hard origin/master

---

# 实用小贴士

内建的图形化 git：

    gitk

彩色的 git 输出：

    git config color.ui true

显示历史记录时，每个提交的信息只显示一行：

    git config format.pretty oneline

交互式添加文件到暂存区：

    git add -i

---
