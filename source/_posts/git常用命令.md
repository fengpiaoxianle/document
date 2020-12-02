---
title: git常用命令
---
####通常提交只需要三个步骤：add、commit、push、pull

* 打开gitbash

* 先进入到项目目录 `cd /d/Proj/cocos/demo/creatorDemo` cd 后直接拖拽文件到命令行

* 克隆Github项目代码到本地 `git clone https://github.com/xxxx.git`

* 添加所有文件`git add .`或`git add -A`
	`git add *js` 添加"js"结尾的文件
	`git add readme.md` 添加当前目录下的readme.md文件

* 提交本地库`git commit -m "描述"`

* 推送到远程库`git push gitee master`，"gitee"是配置中的仓库名
  推送到第二个配置的远程库，如果上面命令失败(首次推送可能会失败)，则用`git push -f github master`

* 查看有没有变更`git status`

* 删除文件，有两种方法
	方法一： `git rm "file path"`
	方法二： 先手动删除文件，`git add .`(`git add "file path"`)或`git rm "file path"`

* 误删还原文件 `git checkout --filePath`

* 拉取文件，更新本地文件，同步远程库代码`git pull <远程主机名> <远程分支名>:<本地分支名>`。如，`git pull gitee master` ，"gitee"为下文配置的仓库名

####添加多个不同仓库，如gitee(码云)，github

`.git`文件夹下`config`文件。后面追加的另一个库。
```
​[core]
	repositoryformatversion = 0
	filemode = false
	bare = false
	logallrefupdates = true
	symlinks = false
	ignorecase = true
[remote "gitee"]
    url = https://gitee.com/fengpiaoxianle/creatorDemo.git
    fetch = +refs/heads/*:refs/remotes/gitee/*
[remote "github"]
	url = https://github.com/fengpiaoxianle/creatorDemo.git
	fetch = +refs/heads/*:refs/remotes/github/*
```
 查看是否修改成功`git branch -a` 目前来看，提交两个库成功后，才能看见。