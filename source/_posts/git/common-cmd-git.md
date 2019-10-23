---
title: git常用命令
tags: 
- git
categories: 
- git
---

> Git 是一个开源的分布式版本控制软件。自诞生以来，Git 就以其开源、简单、快捷、分布式、高效等特点，应付了类似 Linux 内核源代码等各种复杂的项目开发需求。如今，Git 已经非常成熟，被广泛接受与使用，越来越多的项目都迁移到 Git 仓库中进行管理。

<!-- more -->

## 创建版本库

- `git clone <url>`          克隆远程版本库
- `git init`                         初始化本地版本库



## 全局设置

- `git config --global user.name "mayongze"`  设置全局git用户名
- `git config --global user.name "1014057907@qq.com"` 设置全局邮箱



## 修改和提交

- `git status`                     查看状态
- `git diff`                         查看变更内容
- `git add .`                       跟踪所有改动过的文件
- `git add <file>`            跟踪指定的文件
- `git mv <old> <new>`    文件改名
- `git rm <file>`               删除文件
- `git rm --cached <file>`                停止跟踪文件但不删除
- `git commit -m "commit message"`            提交所有更新过的文件
- `git commit --amend`         提交最后一次提交



## 查看提交历史

- `git log`         查看提交历史
- `git log -p <file>`    查看指定文件的提交历史
- `git blame <file>`     以列表方式查看指定文件的提交历史



## 撤销

- `git reset --hard HEAD`    撤销工作目录中所有未提交文件的修改内容
- `git checkout HEAD <file>`    撤销指定的未提交文件的修改内容
- `git revert <commit>`    撤销指定的提交



## 分支与标签

- `git branch`     显示所有本地分支
- `git checkout <branch/tag>`  切换到指定分支或标签
- `git checkout -b 本地分支名x origin/远程分支名x` 拉取远程分支并创建本地分支
- `git branch <new-branch>`   创建新分支
- `git branch -d <branch>`     删除本地分支
- `git tag`        列出所有本地标签
- `git tag <tagname>`   基于最新提交创建标签
- `git tag -d <tagname>`   删除标签




## 合并与衍合

- `git merge <branch>`   合并指定分支到当前分支
- `git rebase <branch>`   衍合指定分支到当前分支



## 远程操作

- `git branch -a ` 查看所有分支包括远程分支
- `git remote -v`    查看远程版本库信息
- `git remote show <remote>`               查看指定远程版本库信息
- `git remote add <remote> <url>`    添加远程版本库
- `git remote show` 更新git分支信息到本地
- `git fetch <remote>`                           从远程库获取代码
- `git pull <remote> <branch>`          下载代码及快速合并
- `git push <remote> <branch>`         上传代码及快速合并
- `git push <remote> :<branch/tag-name>`   删除远程分支或标签
- `git push -u <remote> --tags` 上传所有标签
- `git push -u <remote> --all` 上传全部代码到远程仓库



## 操作例子

### 创建一个新的仓库

```bash
git clone git@github.com:mayongze/name.git
cd nedis
touch README.md
git add README.md
git commit -m "add README"
git push -u origin master
```



### 对已经存在的文件夹进行初始化

```bash
cd existing_folder
git init
git remote add origin git@github.com:mayongze/nedis.git
git add .
git commit -m "Initial commit"
git push -u origin master
```



### 对已经存在的git仓库填写新的远程仓库

```bash
cd existing_repo
#origin 为新远程仓库的name
git remote add origin git@github.com:mayongze/nedis.git
git push -u origin --all
git push -u origin --tags
```

