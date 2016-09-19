---
title: Git 学习记录
tags: git linux
toc: true
description: 工作中遇到的Git操作相关的点点滴滴
categories: git
date: 2016-09-19 11:07:48
---


### git 查看一个文件的历史记录

**1.`git log`**

查看一个文件的改动历史
```shell
git log --pretty=oneline 文件名
```
运行实例
```shell
Administrator@MS-20160715YRXA MINGW32 /e/Work/blog/bingofan.github.io (hexo)
$  git log --pretty=oneline _config.yml
06e6afb1c695f54620ada8523c915dbb62450d0e Search&Share : Remove bdshare Fix https&http request.
020b0d9a1fe4145093319a1f718d3a4a7b8d81e7 Add : Highlight Code Block Function
fb2e4ab6554d3ebed813c7c94d5b1fedd5195317 +) HighLight : Add highlight.js code highlight style.
ae75519920a22b40093af0c0c95f81d56a47d379 FistCommit : Upload hexo file
```

<!-- more -->
**2.`git show`**

查看某一个提交的具体改动
```shell
Administrator@MS-20160715YRXA MINGW32 /e/Work/blog/bingofan.github.io (hexo)
$ git show 06e6afb1c695f54620ada8523c91
commit 06e6afb1c695f54620ada8523c915dbb62450d0e
Author: bingofan <zhaoyuhit@gmail.com>
Date:   Mon Sep 12 12:36:36 2016 +0800

    Search&Share : Remove bdshare Fix https&http request.

    1.修复http请求出错的问题.
    2.去掉百度分享的widget.

diff --git a/_config.yml b/_config.yml
index 380aa71..5705764 100644
--- a/_config.yml
+++ b/_config.yml
@@ -50,7 +50,7 @@ hljs:
   label:
     left: Code
     right: ':'
-    copy: Copy Code
+    copy:

 # Category & Tag
 default_category: uncategorized
```

