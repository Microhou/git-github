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
2. 快速合并， 当前分支和合并分支有共同的祖先时，可以使用快速合并，即直接将当前分支指向合并分支的最新提交。其实就是将当前分支的指针指向合并分支的最新提交。

## git rebase
1. git rebase <branchName> 将当前分支的提交应用到目标分支上
2. git rebase -i <commit> 交互式rebase，可以对提交进行修改、删除、合并等操作
3. git rebase --abort 取消rebase操作
4. git rebase (发生了什么) 
    - 当我们发生变基操作时，git会找到当前分支和目标分支的共同祖先，
    - 对比当前分支相对于祖先的历史提交，并且他们提出出来，存储到一个临时文件中
    - 将当前的部分指向到目标的基底。
5. git rebase 后， 记得要使用git merge 合并分支, 
> git merge and git rebase 对于合并分支来说都是一样的。但是 git rebase 的好处是，合并后的历史提交记录是线性的.
> 如果代码已经提交到了远程仓库，尽量不要使用 git rebase，否则会导致代码混乱。

## git remote 远程仓库
`git remote add origin https://github.com/Microhou/git-github.git`
1. git remote add <remoteName> <remoteUrl> 添加远程仓库
2. git remote remove <remoteName> 删除远程仓库
3. git remote rename <oldName> <newName> 重命名远程仓库
4. git remote set-url <remoteName> <remoteUrl> 设置远程仓库的URL
5. git remote -v 查看远程仓库的URL
6. git remote show <remoteName> 查看远程仓库的信息
7. git fetch <remoteName> 获取远程仓库的最新信息
8. git push <远程库> <本地分支>:<远程分支>
9. git clone https://github.com/Microhou/git-github.git hello 克隆远程仓库到hello
10. git pull  # 从服务器上拉取代码并自动合并

> 本地 仓库和远程仓库是独立的。
> 如果本地库的版本低于远程，则不能push，需要先pull，然后再push。
> 使用git fetch 后，必须手动merge，才能合并到本地库。 `git merge origin/main`
## git push
`git push origin master:master`
1. git push <远程库> <本地分支>:<远程分支>
2. git push <远程库> <本地分支>
3. git push <远程库> --delete <远程分支>
4. git push <远程库> --tags
5. git push <远程库> --all
6. git push <远程库> --force

## git tag
1. git tag <tagName> 创建一个标签
2. git tag -a <tagName> -m "commit message" 创建一个带有说明的标签
3. git tag -d <tagName> 删除一个标签
4. git push <远程库> <tagName> 推送一个标签到远程仓库
