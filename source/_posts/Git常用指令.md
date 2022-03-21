---
title: Git常用指令
date: 2022-03-13 15:02:27
tags:
    - Git
    - 经验分享
categories: 编程开发
description: Git是目前世界上最先进的分布式版本控制系统
---
git常用指令集合
### GIT BASICS
+ __git init__ 
在指定的⽬录下创建⼀个空的git repo。不带参数将在当前⽬录下创建⼀个git repo。
+ __git clone <repo>__
克隆⼀个指定repo到本地。指定的repo可以是本地⽂件系统或者由HTTP或SSH指定的远程路径。
+ __git config user.name `<name>`__
针对当前repo配置⽤户名。使⽤--global参数将配置全局⽤户名。
+ __git add `<directory>`__ 
将指定⽬录的所有修改加⼊到下⼀次commit中。把`<directory>`替换成`<file>`将添加指定⽂件的修改。
+ __git commit -m `"<message>"`__
提交暂存区的修改，使⽤指定的`<message>`作为提交信息，⽽不是打开⽂本编辑器输⼊提交信息。
+ __git status__
显示哪些⽂件已被staged、未被staged以及未跟踪(untracked)。
+ __git log__
以缺省格式显示全部commit历史。更多⾃定义参数请参考后续部分。键盘`q`退出。

### GIT DIFF
+ __git diff__
⽐较⼯作区和暂存区的修改。
+ __git diff HEAD__
⽐较⼯作区和上⼀次commit后的修改。
+ __git diff --cached__
⽐较暂存区和上⼀次commit后的修改。

### UNDOING CHANGES
+ __git revert `<commit>`__
对指定`<commit>`创建的一个undo的commit，并应用到当前分支
+ __git reset `<file>`__
将`<file>`从暂存区移除，但保持工作区不变。此操作不会修改工作区的任何文件。

### REWRITING GIT HISTORY
+ __git oommit -m `<message>` --amend__
将当前staged修改合并到最近一次的commit中。
+ __git rebase `<base>`__
基于`<base>`对当前分支进行rebase。`<base>`可以是commit、分支名称、tag或相对于HEAD的commit.
+ __git reflog__
显示本地repo的所有commit日志。

### GIT BRANCHES
+ __git branch__
显示本地repo的所有分支
+ __git switch -c `<branch>`__
创建并切换到一个新的名为`<branch>`的分支。去掉参数-c将切换到一个已有的分支。
+ __git merge `<branch>`__
将指定`<branch>`分⽀合并到当前分⽀。

### REMOTE REPOSITORIES
+ __git remote add `<name>` `<url>`__
添加一个新的远程连接。添加后可以使用`<name>`作为指定`<url>`远程连接的名称。
+ __git fetch `<remote>` `<branch>`__
从指定`<remote>`抓取指定`<branch>`的所有commit到本地repo。去掉`<branch>`将抓取远程所有分⽀的修改。
+ __git pull `<remote>`__
从指定`<remote>`抓取所有分支的commit并立刻合并到本地repo。
+ __git push `<remote>` `<branch>`__
将本地指定`<branch>`推送到指定远程`<remote>`。如果远程没有对应的分⽀，将⾃动在远程创建此分⽀。

### GIT CONFIG
+ __git config --global user.name `<name>`__
配置当前⽤户名，使⽤--global参数将针对当前系统登录⽤户⽣效。
+ __git config --global user.email `<email>`__
配置当前⽤户Email。
+ __git config --global alias. `<alias-name>` `<git-command>`__
配置⼀个git命令的快捷⽅式。例如：配置”alias.glog log --graph --oneline”使”git glog”相当于”git log --graph --oneline”。
+ __git config --system core.editor `<editor>`__
配置⽂本编辑器，例如vi，在必要时⾃动打开此⽂本编辑器。
+ __git config --global --edit__
打开当前⽤户的git全局配置并编辑。

### GIT LOG
+ __git log -`<limit>`__
限制log的显示数量。例如：”git log -5”仅显示最新5条commit。
+ __git log --online__
每行显示一条commit。
+ __git log --author="`<pattern>`"__
按提交者名字搜索并显示commit。
+ __git log --grep="`<pattern>`"__
按指定内容搜索并显示commit。
+ __git log `<since>`..`<until>`__
显示指定范围的commit。范围参数可以是commit ID、分⽀名称、HEAD或任意相对位置。
+ __git log -- `<file>`__
仅显示包含指定文件修改的commit。
+ __git log --graph__
使用--graph参数显示图形化的branch信息。

### GIT RESET
+ __git reset__
移除所有暂存区的修改，但不会修改⼯作区。
+ __git reset --hard__
移除所有暂存区的修改， 并强制删除所有工作区的修改。
+ __git reset `<commit>`__
将当前分支回滚到指定`<commit>`，清暂存区的修改，但保持工作区状态不变。
+ __git reset --hard `<commit>`__
将当前分⽀回滚到指定`<commit>`，清除暂存区的修改，并强制删除所有⼯作区的修改。

### GIT REBASE
+ __git rebase -i `<base>`__
以交互模式对当前分支做rebase。

### GIT PULL
+ __git pull --rebase `<remote>`__
抓取所有远程分⽀，并以rebase模式并⼊本地repo⽽不是merge。

### GIT PUSH
+ __git push `<remote>` --force__
将本地分支推送到远程。不要使用--force参数，除非完全明白这个操作。
+ __git push `<remote>` --tags__
使⽤push命令并不会⾃动将本地tag推送到远程。加上--tags参数会将所有本地tag推送到远程。

