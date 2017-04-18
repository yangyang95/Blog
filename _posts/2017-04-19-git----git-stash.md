---
layout: post
title: "Git 使用心得 - git stash"
description: ""
date: 2017-04-19
tags: [git]
comments: true
---

## 指令介紹
最近使用 git 的時候學習到一個好用的功能 `$ git stash`

所謂的 stash 就是儲藏的意思，主要的用處就是在 `pull` 或 `checkout` 之前，
如果有尚未完成的工作都可以先執行 stash ，將工作存起來再執行。

這功能在與他人共同協作的時候特別有用。以下舉例來說明：

```bash
$ git status
# On branch master
# Changes to be committed:
#   (use "git reset HEAD <file>..." to unstage)
#      modified:   main.c
#
# Changes not staged for commit:
#   (use "git add <file>..." to update what will be committed)
#
#      modified:   matrix.h
#
```

可以看到 main.c 已經 stage，然後 matrix.h 還沒有。執行 **commit** 後，<br>
如果需要進行 **push**，就勢必需要將還沒 commit 的檔案先 **stash** 起來。

可以用 `$ git stash list` 來查看被儲存起來的東西
```bash
$ git stash list
stash@{0}: WIP on master: 049d078 added the index file
stash@{1}: WIP on master: c264051 Revert "added file_size"
stash@{2}: WIP on master: 21d80a5 added number to log
```

完成更改後，重新把存起來的更改抓回來用 `$ git stash apply`

## 小結
我使用到的指令：<br>
`$ git stash` - 儲存更改<br>
`$ git stash list` - 列出儲存<br>
`$ git stash apply` - 抓回儲存<br>
目前這三個就很足夠我使用了

其他的指令可以在參考連結查看
* [Git 工具 - 儲藏 (Stashing)](https://git-scm.com/book/zh-tw/v1/Git-%E5%B7%A5%E5%85%B7-%E5%84%B2%E8%97%8F-Stashing)
* [Stash（暫存）](https://backlogtool.com/git-guide/tw/reference/stash.html)
* [Git rebase + stash 小技巧](https://blog.wu-boy.com/2013/08/git-rebase-stash-tip/)