---
title: css高级技巧
date: 2017-12-08 15:36:00
tags: css
---

### **css代码检测以及项目规范**

1.不要使用多个class选择元素，如a.foo.boo，这在ie6及以下不能正确解析
<!-- more -->


### css Icon收藏
http://cssicon.space/#/

### css高级绘制技巧

* border border-radius
* after before
* box-shadow
* linear-gradient 
* radial-grandient

### BFC的概念生成和使用场景
**概念**
Box: CSS布局的基本单位

**如何生成BFC**
根元素

**BFC元素的特点**
根据BFC布局规则：
3.计算BFC的高度时，浮动元素也参与计算

**BFC的使用场景**

* 自适应布局
* 清楚内部浮动
* 防止margin重叠

### 移动端PX和REM的换算

different size  different DPR
### ie6中的经典bug



1、IE6怪异解析之padding与border算入宽高 
4、内部盒模型超出父级时，父级被撑大 
10、li之间会有间距 
