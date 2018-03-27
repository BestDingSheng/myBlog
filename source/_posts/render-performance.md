---
title: 网页性能管理详解
date: 2018-03-06 10:59:56
tags:
---

### Timeline 掌握针渲染模式

1 网页动画能够做到每秒60帧，就会跟显示器同步刷新，一秒之内进行60次重新渲染，每次重新渲染的额时间不能超过16.66毫秒

蓝色 网络通信和HTML解析
黄色 javascript 执行
紫色 样式计算和布局，即重排
绿色 重绘
window.requestAnimationFrame() 下一次
window.requesrldelCallback()下几次重新渲染时

<!-- more -->

### 触发分层

1 获取DOM 并将其分割为多个层
2 将每个层独立的绘制进位图中
3 将层作为纹理上传至GPU
4 复合多个层来生成最终的屏幕图像


1 DOM子树渲染层（renderLayer）
根元素 position transform 半透明 css滤镜 Canvas2d video 溢出
2 Compositor 渲染层子树的图形层（GraphicsLayer）
css3的透视 video webgl transform 加速css滤镜 叠加在已经触发合成层


### 触发浏览器重排和重绘

1 样式表越简单，重排和重绘就越快。
2重排和重回的DOM元素层级越高，成本就越高
3 table元素的重排和重绘成本，要高于div元素
4 尽量不要把读操作和写操作，放在一个语句里面
5 统一改变样式
6 缓存重排结果
7离线MDO Fragment/clone
8 虚拟Dom React。
9 必要的时候display：node 不见原色不影响重排重绘。


网页生成的时候，至少会渲染一次，用户访问过程中还会不断的重新渲染，一下三种情况会导致网页的重新渲染。
1 修改DOM
2 修改样式表
3 用户事件
重新渲染 就需要重新生成布局和重新绘制。前者叫做重排，后者重绘。
需要主要的是，重回不一定重排。 比如改变某个元素的颜色，就只会出发重绘，不会触发重排 因为布局没有改变。但是重排一定会出发重绘，比如改变一个元素的位置就会同时触发 重排和重绘 因为布局改变了。

###  参考资料

http://www.ruanyifeng.com/blog/2015/09/web-page-performance-in-depth.html









