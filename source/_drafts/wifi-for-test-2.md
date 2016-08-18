---
title: wifi for test 2
date: 2016-08-12 10:27:59
tags: themes
categories: wiki-TestCati1
description: "A list of all the official color themes."
shadow: true
feature: /images/color-themes.png
toc: true
---


参数 描述 
start 必需。一个非负的整数，规定要提取的子串的第一个字符在 stringObject 中的位置。 
stop 可选。一个非负的整数，比要提取的子串的最后一个字符在 stringObject 中的位置多 1。如果省略该参数，那么返回的子串会一直到字符串的结尾。 

返回值 
一个新的字符串，该字符串值包含 stringObject 的一个子字符串，其内容是从 start 处到 stop-1 处的所有字符，其长度为 stop 减 start。 

说明 
substring 方法返回的子串包括 start 处的字符，但不包括 end 处的字符。 
如果 start 与 end 相等，那么该方法返回的就是一个空串（即长度为 0 的字符串）。 
如果 start 比 end 大，那么该方法在提取子串之前会先交换这两个参数。 
如果 start 或 end 为负数，那么它将被替换为 0。 
