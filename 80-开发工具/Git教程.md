---
banner: "https://api.dujin.org/bing/1920.php"
cssclass: noyaml,noscroll,myhome
obsidianUIMode: preview
banner_x: 0.5
banner_y: 0.5
---

#GitHub #Git #开发工具 

# Git 简介

Git 是目前世界上最先进的分布式==版本控制系统==。

版本控制系统（version control system）, 是一种==记录一个或若干文件内容变化==，以便将来查阅特定版本修订情况的系统。

## Git 的诞生

Git 是由 Linux 之父 Linus 开发的，在 2005 年 4 月 3 号开始开发，到 4 月 7 号仅四天时间 Git 就可以投入使用了。到同年 6 月份，Linux 已经在使用 Git 管理代码了。

Git 是用什么语言开发的：==C 语言==。

## 集中式 vs 分布式

>集中式和分布式的区别是：
你的本地是否有完整的版本库历史！
假设 SVN 服务器没了，那你丢掉了所有历史信息，因为你的本地只有当前版本以及部分历史信息。必须联网才能工作。
假设 GitHub 服务器没了，你不会丢掉任何 git 历史信息，因为你的本地有完整的版本库信息。你可以把本地的 git 库重新上传到另外的 git 服务商。可以离线工作。

# 安装 Git

在 Windows 上使用 Git，可以从 Git 官网直接[下载安装程序](https://git-scm.com/downloads)，然后按默认选项安装即可。

安装完成后，在开始菜单里找到“Git”->“Git Bash”，会出现一个类似如下图命令行窗口的东西，就说明 Git 安装成功！
![](https://obsidian-picture.oss-cn-qingdao.aliyuncs.com/my-img/Git教程1.png)
# Git 初始化
## 设置用户签名

> 签名的作用就是用来标识用户，以区分不同的开发人员

==安装完成后，还需要最后一步设置，==在命令行输入：

```bash
$ git config --global user.name "Your Name"
$ git config --global user.email "email@example.com"
```

注意 `git config` 命令的 `--global` 参数，用了这个参数，表示你这台机器上所有的 Git 仓库都会使用这个配置，当然也可以对某个仓库指定不同的用户名和 Email 地址。
## 初始化仓库

==如果你使用 Windows 系统，为了避免遇到各种莫名其妙的问题，请确保目录名（包括父目录）不包含中文。==

通过 `git init` 命令可以把目录变成 Git 可以管理的仓库：

```bash
# git 初始化的指令
$ git init
```

瞬间 Git 就把仓库建好了，而且告诉你是一个空的仓库（empty Git repository），可以发现当前目录下多了一个 `.git` 的目录，这个目录是 Git 来跟踪仓库的，没事千万不要手动修改这个目录里面的文件，不然改乱了，就把 Git 仓库给破坏了。

如果你没有看到 `.git` 目录，那是因为这个目录默认是隐藏的，用 `ls -ah` 命令就可以看见。

==也不一定必须在空目录下创建 Git 仓库，选择一个已经有东西的目录也是可以的。==

# Git 工作机制
分为 Git 工作区、暂存区和版本库
==具体流程：代码提交到暂存区（暂时保存），然后暂存区提交到 master 分支（版本库）==
## Git 工作区
在电脑里面能够看得到的项目目录，但是项目目录下隐藏了一个 `.git` 目录，这个目录不属于工作区，而是版本库
## Git 暂存区
英文叫 stage 或 index。一般存放在 .git 目录下的 index 文件（.git/index）中，所以我们把暂存区有时也叫作索引（index）。
## Git 版本库
`.git` 目录就是版本库

# 托管平台
+ 局域网（内网）
	+ GitLab
+ 公网（外网）
	+ GitLab
	+ GitHub
	+ Gitee
# 添加文件到暂存区
我们要放入暂存区，要使用 `git add` 命令
+ 把单独一个文件放在暂存区
```bash
# 把文件夹下的index.txt文本放在暂存区
$ git add index.txt
```
+ 把单独一个文件夹放在暂存区（==暂存区不能存放空文件夹==）
```bash
# 把文件夹下的test文件夹放在暂存区
$ git add test/
```
+ 把所有文件都放在暂存区
```bash
# 把文件夹下所有的内容都放在暂存区
$ git add --all
# git add --all 有一个简单的写法
$ git add .
```
==可以使用 `git status` 命令来掌握仓库当前的状态==
==可以使用 `git rm --cached <file>...` 命令来从暂存区中删除 file==

# 提交暂存区到本地仓库
将暂存区文件提交到本地仓库，使用 `git commit` 命令
```bash
# 把暂存区的内容放到本地仓库
$ git commit -m "备注"
```
我们使用 `git log` 命令来查看版本信息
```bash
# 查看当前历史区版本信息
$ git log
```

# 版本穿梭
## 版本回退
使用 `git reset --hard 版本编号` 进行版本回退（回退到工作区）
```bash
# 回退到上一次提交的版本
$ git reset --hard HEAD^
# 回退到上上次提交的版本
$ git reset --hard HEAD^
$ git reset --hard HEAD~2
```
Git 的版本回退速度非常快，因为 Git 在内部有个指向当前版本的 `HEAD` 指针，当你回退版本的时候，Git 仅仅是把 HEAD 从指向 `当前版本` ，改为指向 `要回到的版本` 
![](https://obsidian-picture.oss-cn-qingdao.aliyuncs.com/my-img/Git教程2.gif)

然后顺便把工作区的文件更新了。所以你让 `HEAD` 指向哪个版本号，你就把当前版本定位在哪。
==如果回退错了，可以使用 `git reflog` 命令来查看所有的操作记录，可以通过前面的标识符（版本号）来回退==
使用 `git reset --soft 版本编号` 可以回退到暂存区，用处：备注重写和版本合并
## git revert 和 git reset
+ git reset 是回滚到对应的 commit-id，相当于是删除了 commit-id 以后的所有的提交，并且不会产生新的 commit-id 记录，如果要推送到远程服务器的话，需要强制推送-f
+ git revert 是反做撤销其中的 commit-id，然后重新生成一个 commit-id。本身不会对其他的提交 commit-id 产生影响，如果要推送到远程服务器的话，就是普通的操作 git push 就可以
git reset：
![](https://obsidian-picture.oss-cn-qingdao.aliyuncs.com/my-img/Git教程3.gif)
git revert：
![](https://obsidian-picture.oss-cn-qingdao.aliyuncs.com/my-img/Git教程4.gif)
# Git 分支
## 初识分支
+ `git` 分支，就是我们自己把我们的整个文件夹分成一个一个独立的区域
+ 比如我们在开发 `登录` 功能的时候，可以放在 `login` 分支下进行开发；在开发 `列表` 功能的时候，可以放在 `list` 分支下进行开发，大家互不干扰，每一个功能都是一个独立的功能分支，这样开发会更好
+ `git` 在初始化的时候，会自动生成一个分支，叫做 `master`，是表示主要分支的意思
+ 我们可以自己开辟出很多独立分支
## 分支管理
+ 开辟一个分支，使用 `git branch 分支名称` 命令
```bash
# 开辟一个login分支
$ git branch login
```
+ 查看一下当前分支情况，前面有个 `*` 的，并且有高亮显示的，表示你当前所处的分支
```bash
# 查看当前分支情况
$ git branch
```
+ 切换分支（HEAD 指向会跟着一起变），使用 `git checkout 分支名称` 命令
```bash
# 切换到master分支
$ git checkout master
```
==注意：切换分支时，记得将当前分支提交到暂存区（git add）==
+ 合并分支，使用 `git merge 分支名称` 命令
```bash
# 合并login分支到master分支
# 首先切换到master分支
$ git checkout master
# 合并分支
$ git merge login
```
+ 删除分支，使用 `git branch -d 分支名称` 命令
```bash
# 删除login分支
# 先切换到别的分支
$ git checkout master
# 删除login分支
$ git branch -d login
```
## 分支合并冲突
分支合并后如有冲突，git 会在文件中标识出来，需要我们人工解决冲突
# 初识团队协作
需要使用托管平台来实现，如 GitHub
## GitHub 远端仓库
首先，登陆 GitHub，然后，在右上角找到“Create a new repo”按钮，创建一个新的仓库，在 Repository name 填入你的仓库名，其他保持默认设置，点击“Create repository”按钮，就成功地创建了一个新的 Git 仓库。

目前，在GitHub上的这个仓库还是空的，GitHub告诉我们，可以从这个仓库克隆出新的仓库，也可以把一个已有的本地仓库与之关联，然后，把本地仓库的内容推送到GitHub仓库。

现在，我们根据 GitHub 的提示，在本地的要上传的仓库下运行命令：

```bash
$ git remote add origin git@github.com:你的账户名/你的仓库名.git
# 如：$ git remote add origin git@github.com:zhf521/learngit.git
# 这里的origin是你的远端库的别名，可以是任意的，以后你提交的时候就可以向origin提交即可
# 使用 $ git remote remove origin git@github.com:你的账户名/你的仓库名.git命令即可删除
```
使用 `git remote -v` 可以查看连接的远程库
## 推送
使用 `git push` 推送
```bash
$ git push origin master
# 将本地分支推送到远程库（别名为origin）master分支上
```
加上 `-u` 参数即可以后只使用 `git push` 来推送
```bash
$ git push -u origin master
```
## 拉取
使用 `git pull` 拉取更新的文件
```bash
$ git pull origin master
# 将远程库（别名为origin）master分支拉取到本地分支上
```
加上 `-u` 参数即可以后只使用 `git pull` 来推送
```bash
$ git pull -u origin master
```
## 克隆
使用 `git clone 仓库地址` 克隆远程仓库里面的内容到本地==（注意：克隆只能克隆主分支）==
可以克隆别人的公开的仓库，也可以克隆自己的仓库，克隆别人的仓库，我们只能拿来用，修改后不能重新上传；克隆自己的仓库，我们修改后还可以再次上传更新
```bash
# 直接克隆仓库
$ git clone 仓库地址
```
# 团队协作的分支管理
本地分支推送到远程分支
使用 `git push` 推送
```bash
$ git push origin login
# 将本地分支推送到远程库（别名为origin）login分支上
```
==注意：克隆只能克隆主分支，需要拉取分支==
使用 `git pull` 拉取更新的文件
```bash
$ git pull origin login
# 将远程库（别名为origin）login分支拉取到本地分支上
```
删除远程分支
```bash
$ git pull origin :login
# 将远程库（别名为origin）login分支删除
```
# 跨团队协作
先 fork 到自己的仓库，然后修改，然后 pull request，等待原作者审核
# VSCode 集成 Git
 [[VSCode|VSCode]] 中已经集成了 Git
 `.gitignore` 文件可以忽略文件，这个文件将不会上传
 # 一图总结
![](https://obsidian-picture.oss-cn-qingdao.aliyuncs.com/my-img/Git教程5.png)
