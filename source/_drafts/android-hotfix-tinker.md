---
title: Tinker使用记录
toc: true
description: '初次尝试使用Tinker做Android热修复'
tags:
	android
	hotfix
	热修复
categories:
	android
---

### Tinker 说明
项目地址 >>> [Tinker Git](https://github.com/Tencent/tinker)
官方接入指南 >>> [Tinker 接入指南](https://github.com/Tencent/tinker/wiki/Tinker-%E6%8E%A5%E5%85%A5%E6%8C%87%E5%8D%97)

以下为官方说明摘录:
Tinker是微信官方的Android热补丁解决方案，它支持动态下发代码、So库以及资源，让应用能够在不需要重新安装的情况下实现更新。当然，你也可以使用Tinker来更新你的插件。

它主要包括以下几个部分：

* gradle编译插件: tinker-patch-gradle-plugin
* 核心sdk库: tinker-android-lib
* 非gradle编译用户的命令行版本: tinker-patch-cli.jar

<!-- more -->
本文用来记录参照官方接入指南完成热修复功能,记录期间遇到的各种问题。


