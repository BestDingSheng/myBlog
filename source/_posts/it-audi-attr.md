---
title: H5-audio标签的基础使用
date: 2017-07-10 14:46:52
tags: html
---

> 这两天在做音乐播放器使用的是h5的audio标签~
> 之前没这么接触过这个下面列出下audio的常用属性和方法

### 属性
* duration // 获取视频的总时间 返回秒
* currenttime // vuido的当前时间

<!--more-->

### 方法
* play // 播放
* pause // 暂停

### 事件
* ontimeupdate 事件。在用户开始播放视频，或者移动视频的播放位置时触发函数，
* ended   vudio播放完成触发该函数
* canplay vudio加载完成触发该函数

