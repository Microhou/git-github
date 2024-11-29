# git-github

## 1. git简介
### 1.1 什么是git
Git是一个开源的分布式版本控制系统，用于敏捷高效地处理任何或小或大的项目。

### 1.2 什么是版本控制
版本控制是一种记录一个或若干文件内容变化，以便将来查阅特定版本修订情况的系统。

### 1.3 什么是分布式版本控制系统
分布式版本控制系统（Distributed Version Control System，简称 DVCS）和集中式版本控制系统（Centralized Version Control System，简称 CVCS）的区别

## 2. git安装
### 2.1 git安装
#### 2.1.1 windows
1. 下载地址：https://git-scm.com/download/win
2. 安装完成后，在命令行输入`git --version` `git -v`，如果出现版本号，则说明安装成功。
3. 配置用户名和邮箱 `git config --global user.name "your name"` `git config --global user.email "your email"`
4. 查看配置信息 `git config --list`
5. 查看用户名和邮箱 `git config user.name` `git config user.email`
6. 查看git安装路径 `where git`
7. 查看git安装目录 `git --exec-path`
8. 初始化git仓库 `git init`
9. 查看git仓库状态 `git status`

## git 文件管理
### 2.2 git文件管理
#### 2.2.1 git文件状态
1. 未跟踪（Untracked）and 已经跟踪（Tracked）
2.  暂存
3.  未修改
4.  已修改
- 刚刚添加的文件， 是未跟踪状态，需要使用`git add <file>`命令添加到暂存区，然后使用`git commit -m "commit message"`命令提交到本地仓库。

#### 2.2.2 git文件操作
1. 添加文件到git仓库 `git add <file>` `git add *` `git add .` `git commit -a -m "commit message"` 提交所有已修改的文件
2. git restore <file> 恢复暂存区的指定文件到工作区  git restore --staged <file> 恢复暂存区的指定文件到工作区

3. git rm <file> 删除工作区文件，并且将这次删除放入暂存区
4. git rm -f <file> 强制删除工作区文件，并且将这次删除放入暂存区

5. git mv [-v] [-f] [-n] [-k] <源文件> <目标文件> 移动或重命名一个文件、一个目录或一个符号链接

## git 分支
1. git branch <branchName>
2. git checkout <branchName> 
3. git switch <branchName> 切换分支
4. git branch -d <branchName> 删除分支
5. git switch -c <branchName> 创建并切换到新的分支

## git merge 
1. git merge <branchName> 合并指定分支到当前分支
