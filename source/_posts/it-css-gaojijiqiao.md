---
title: css高级技巧
date: 2017-12-08 15:36:00
tags: css
---

### **css代码检测以及项目规范**

1.不要使用多个class选择元素，如a.foo.boo，这在ie6及以下不能正确解析2.移除空的css规则，如a{}3.正确的使用显示属性，如display:inline不要和width，height，float，margin,padding同时使用，display:inline-block不要和float同时使用等4.避免过多的浮动，当浮动次数超过十次时，会显示警告
<!-- more -->5.避免使用过多的字号，当字号声明超过十种时，显示警告6.避免使用过多web字体，当使用超过五次时，显示警告7.避免使用id作为样式选择器8.标题元素只定义一次9.使用width:100%时要小心10.属性值为0时不要写单位11.各浏览器专属的css属性要有规范，例如.foo{-moz-border-radius:5px;border-radius:5px}12.避免使用看起来像正则表达式的css3选择器13.遵守盒模型规则


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
Box: CSS布局的基本单位Box 是 CSS 布局的对象和基本单位， 直观点来说，就是一个页面是由很多个 Box 组成的。元素的类型和 display 属性，决定了这个 Box 的类型。 不同类型的 Box， 会参与不同的 Formatting Context（一个决定如何渲染文档的容器），因此Box内的元素会以不同的方式渲染。让我们看看有哪些盒子：block-level box:display 属性为 block, list-item, table 的元素，会生成 block-level box。并且参与 block fomatting context；inline-level box:display 属性为 inline, inline-block, inline-table 的元素，会生成 inline-level box。并且参与 inline formatting context；Formatting context 是 W3C CSS2.1 规范中的一个概念。它是页面中的一块渲染区域，并且有一套渲染规则，它决定了其子元素将如何定位，以及和其他元素的关系和相互作用。最常见的 Formatting context 有 Block fomatting context (简称BFC)和 Inline formatting context (简称IFC)。

**如何生成BFC**
根元素float属性不为noneposition为absolute或fixeddisplay为inline-block, table-cell, table-caption, flex, inline-flexoverflow不为visible

**BFC元素的特点**
根据BFC布局规则：1.每个元素的margin box的左边， 与包含块border box的左边相接触(对于从左往右的格式化，否则相反)。即使存在浮动也是如此。2.BFC的区域不会与float box重叠。
3.计算BFC的高度时，浮动元素也参与计算

**BFC的使用场景**

* 自适应布局
* 清楚内部浮动
* 防止margin重叠

### 移动端PX和REM的换算

different size  different DPR目前的设计稿 一般是 640 750 1125，一般要先均分成100份，(兼容vh,vm) 750/10 = 75px。div宽是240px*120px css的书写改为3.2rem * 1.6rem。 配合响应式修改html根的大小。字体不建议使用rem的，data-dpr属性动态设置字体大小。屏幕变大放更多的文字，或者屏幕更大放更多的字。神奇的padding/margin-top等比例缩放间距
### ie6中的经典bug



1、IE6怪异解析之padding与border算入宽高 原因：未加文档声明造成非盒模型解析 解决方法：加入文档声明<!doctype html> 2、IE6在块元素、左右浮动、设定marin时造成margin双倍（双边距） 解决方法：display:inline 3、以下三种其实是同一种bug，其实也不算是个bug，举个例子：父标签高度20，子标签11，垂直居中，20-11=9，9要分给文字的上面与下面，怎么分？IE6就会与其它的不同，所以，尽量避免。 1）字体大小为奇数之边框高度少1px 解决方法：字体大小设置为偶数或line-height为偶数 2）line-height，文本垂直居中差1px 解决方法：padding-top代替line-height居中，或line-height加1或减1 3）与父标签的宽度的奇偶不同的居中造成1px的偏离 解决方法：如果父标签是奇数宽度，则子标签也用奇数宽度;如果是父标签偶数宽度，则子标签也用偶数宽度 
4、内部盒模型超出父级时，父级被撑大 解决方法：父标签使用overflow:hidden 5、line-height默认行高bug 解决方法：line-height设值 6、行标签之间会有一小段空白 解决方法：float或结构并排(可读性差，不建议) 7、标签高度无法小于19px 解决方法：overflow: hidden; 8、左浮元素margin-bottom失效 解决方法：显示设置高度 or 父标签设置_padding-bottom代替子标签的margin-bottom or 再放个标签让父标签浮动，子标签 margin- bottom，即(margin-bottom与float不同时作用于一个标签) 9、img于块元素中，底边多出空白 解决方法：父级设置overflow: hidden; 或 img { display: block; } 或 _margin: -5px;  
10、li之间会有间距 解决方法：float: left; 11、块元素中有文字及右浮动的行元素，行元素换行 解决方法：将行元素置于块元素内的文字前 12、position下的left，bottom错位 解决方法：为父级(relative层)设置宽高或添加*zoom:1 13、子级中有设置position，则父级overflow失效 解决方法：为父级设置position:relative

