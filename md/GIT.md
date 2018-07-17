
# Git

## 什么是版本控制系统

没有版本控制系统之前。。比如写小说、论文的痛苦，需要手动的去记录每次的改动。能记录每次文件的改动（包括每次改动的时间、作者、内容等），还可以协同其他人协作编辑的一个工具（系统）。

## 版本控制系统的分类

### 集中式版本控制系统

代表：CVS、SVN，版本库放在中央服务器，必须联网才能工作（记录每次的改动）

### 分布式版本控制系统

代表：Git 每个人的电脑就是一个完整的版本库，没有网络也可以工作（记录每次的改动）

## Git的历史

开发Linux系统的那个人用C语言写的Git，最开始Git只能运行在Linux和Unix系统上，后来移植到了Windows上，现在Git可以在Linux、Uniux、Mac、Windows等几大平台上运行。

## Git安装

Linux、Mac这里忽略。。日后去公司需要安装的话百度一下。Windows安装也比较麻烦，不过还好有一个Git面向Windows的打包好的安装程序。（Git-2.10.2-64-bit.exe）默认安装好后，在开始菜单中找到 ‘Git’-》‘Git Bash’ 即可通过Linux命令来操作电脑，从而使用Git。

## Git仓库基本模型

### 工作区（Working Directory）

电脑上的目录，你写代码的地方

### 版本库（Reponsitory）

当初始化一个git仓库后，会生成一个.git隐藏目录，该目录就是Git管理代码的仓库。改仓库又分为两部分。

**1、暂存区（Stage）：**当我们把文件的修改最后提交到仓库前，首先要把文件的修改放到暂存区中。使用git add 操作后就会把工作区的修改添加到暂存区。

**2、主分支（Master Branch）和 其他分支：**Git会为我们自动创建一个默认主分支master，以及一个指向master分支的指针HEAD，git commit 操作后就会把暂存区的文件提交到版本库的当前分支上。

## Git基本命令

以下这2个只配置一次即可，最好配置你github的用户名和邮箱

**配置用户名：**`git config --global user.name '你的用户名（英文)'` 
git
**配置邮箱：**`git config --global user.email '你的邮箱'`

**初始化仓库：**`git init` 在要使用Git管理的目录下执行这个命令，会把当前目录变为Git可以管理的仓库，按照上课最后和github结合使用的流程来说，这个命令是不需要执行的，自己在本地练习git命令的时候可以使用。

**查看仓库状态：**`git status` 查看Git仓库的状态（是否有文件被改动、是否有未提交等），可以使用这个命令来测试某个目录是否由git来管理，对于新手来说，以后每次操作完一个命令，就要不停的使用`git status`，执行这个命令后有以下几种情况。

​	1、如果终端显示的是   **红色**，说明应该执行`git add 文件名` 的操作。

​	2、如果终端显示的是   **绿色**，则说明现在应该执行`git commit -m '提交描述'`的操作。

​	3、如果出现**nothing to commit, working directory clean** 则说明现在的状态和版本库中最新的状态一致。

**添加到暂存区：**`git add 文件名` 或 `git add . `添加工作区文件的修改到暂存区

**提交到分支：**`git commit -m '提交描述'` 将暂存区文件的修改一次性的提交到某个分支中（默认是master主分支）

**查看日志：**就是查看版本的记录。查看日志的方式有以下几种方式

​	1、`git log` 查看日志列表，包含作者、时间、commitId、日志描述等信息

​	2、`git log --pretty=oneline` 格式化查看日志列表，包含commitId 和 日志描述

​	3、`git reflog` 查看所有操作（提交和版本回退）记录的日志，包含精简的commitId 和 日志描述

**版本回退：**`git reset --hard 'commitId(版本号)'`版本回退（把已经提交过的修改，回退到指定的某一个版本），一般配合`git reflog` 来使用

**撤销：**撤销修改分两种情况。

​	1、没有add到暂存区的时候直接使用`git checkout 文件名` 丢弃工作区的修改

​	2、已经add到暂存区的时候，但还没有提交，先通过`git reset HEAD 文件名 `命令把暂存区的修改撤销掉，重新放回工作区，然后在通过`git checkout 文件`丢弃工作区的修改，最后通过`git status`命令测试即可。

**分支相关：**

​	`git branch` 查看分支列表以及当前所在分支

​	`git checkout -b 分支名字` 创建并且切换分支 (并且会把当前分支的代码和管理记录一起发送到新建立的分支中，注意：如果在某个分支下执行这个命令的话，确定要把当前这个分支下的提交弄干净，说白了就是 nothing to commit, working directory clean)

​	`git checkout 分支名字` 切换分支

​	`git branch -d 分支名字` 删除分支

​	`git merge 分支名字` 合并某分支到当前分支





**克隆远程仓库：**`git clone 仓库地址（HTTPS和SSH协议方式都可以）`，克隆好之后，就会在本地生成一个该项目的仓库，不需要在手动去执行`git init`操作。 

**注意：克隆的话一般是刚去公司的时候会克隆一次，以后不需要在克隆，除非你的项目损坏或者丢失。**

**把本地仓库的提交推送到远程仓库：** `git push origin 分支名字`，前提是在你有权限的情况下才可以进行推送操作！！！ git push -u origin 分支名字(第一次时操作更好)

**更新远程仓库的代码：**`git pull origin 分支名字`，我们如果想要远程仓库中最新的代码，首先需要更新一下，特别是在`push`这种操作的时候，如果没有更新到远程仓库最新的代码的话，会被拒绝推送`push`的。



**https协议：**只需要给管理员（创建远程仓库的人github账号），然后人家邀请你，同意下既可有管理权限。

**ssh协议：**生成公钥`ssh-keygen -t rsa -C 'youremail@example.com'`，然后去`C:Users/AdminstroterXXXX/.ssh目录下`找


id_rsa.pub文件，打开把这个添加到 github设置里配置下即可。


<!-- 创建的远程仓库出错时 -->
git remote rm origin
<!-- 在执行 -->
git remote add origin git@github.com:wangjiahao19951021/HK.git


git push origin master


git init
git add README.md
git commit -m "first commit"
git remote add origin https://github.com/wangjiahao19951021/-.git
git push -u origin master


