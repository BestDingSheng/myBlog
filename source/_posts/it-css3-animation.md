---
title: css3 animation详解
date: 2017-12-05 10:21:38
tags: css
---

> 最近在面试中经常会被问到css3的动画属性今天把animation的文档详细看了遍

http://www.w3school.com.cn/css3/css3_animation.asp

| 属性 |	描述 |	CSS |
| --- | --- | --- |
| @keyframes |	规定动画。|	3
|animation |	所有动画属性的简写属性，除了 animation-play-state 属性。|	3
|animation-name	| 规定 @keyframes 动画的名称。	| 3
|animation-duration	|规定动画完成一个周期所花费的秒或毫秒。默认是 0。|	3
|animation-timing-function|	规定动画的速度曲线。默认是 "ease"。|	3
|animation-delay|	规定动画何时开始。默认是 0。	|3
|animation-iteration-count|	规定动画被播放的次数。默认是 1。	|3
|animation-direction	|规定动画是否在下一周期逆向地播放。默认是 "normal"。|	3
|animation-play-state|	规定动画是否正在运行或暂停。默认是 "running"。	|3
|animation-fill-mode|	规定对象动画时间之外的状态。	|3


animation是可以绑定多个动画

animation-fill-mode :forwards 

可以让动画运动完停留在最后一帧

