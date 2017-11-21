---
title: CSS3 3D笔记
date: 2017-10-30 14:31:20
tags: [css]
---

![](http://upload-images.jianshu.io/upload_images/215275-c07f7f3effbc8810.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

http://www.zhangxinxu.com/wordpress/2012/09/css3-3d-transform-perspective-animate-transition/ 了解更多请查看这篇文章

首先了解下在css中3d中比2D多了一个Z轴

Z轴在css3中的属性是 transform: translateZ(100px);

如何做个3D的正方体 

首先需要舞台和元素 

舞台就是父元素 需要添加3D属性 transform-style: preserve-3d;

<!--more-->

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="utf-8">
	<title>
		css高级正方体
	</title>
</meta>
</head>
<style>
.container{
	width: 200px;
	height: 200px;
	border:1px solid red;
	margin: 200px  auto;
	position: relative;
	/*perspective: 600px;*/
	transform-style: preserve-3d;
	animation: haha 10s;

}
.container div{
	width: 200px;
	height: 200px;
	opacity: .8;
	position: absolute;
	color: #fff;
	line-height: 200px;
	text-align: center;
	font-size: 64px;

}
.container div:nth-child(1){
	transform: translateZ(100px);
	background: green;
}
.container div:nth-child(2){
	transform: rotateX(90deg) translateZ(-100px);
	background: yellow;
}
.container div:nth-child(3){
	transform: rotateX(90deg) translateZ(100px);
	background: blue;
}
.container div:nth-child(4){
	transform: rotateY(90deg) translateZ(100px);
	rotateY(90deg) translateZ(100px)
	background: red;
}
.container div:nth-child(5){
	transform: rotateY(90deg) translateZ(-100px);
	background: black;
}
.container div:nth-child(6){
	background: orange;
	transform: translateZ(-100px) rotateY(180deg);
}

@keyframes haha
{
	10% {

		transform: rotateY(0deg)  rotateX(0deg);
	}
	50%{
		transform: rotateY(360deg) rotateX(0deg);
	}
	100%{
		transform: rotateY(360deg) rotateX(360deg);
	}
	
}
</style>
<body>
	<div class="container">
		<div>1</div>
		<div>2</div>
		<div>3</div>
		<div>4</div>
		<div>5</div>
		<div>6</div>
	</div>
</body>
</html>
```

