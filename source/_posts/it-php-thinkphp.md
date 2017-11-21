---
title: thinkphp 学习笔记
date: 2017-06-20 06:58:14
tags: [php,后台]
---


封装个子类 继承thinkphp核心类 须要执行 parent::__construct(); 这个方法才能使用thinkphp 核心类的方法

```php
<?php 
namespace Admin\Controller;
use Think\Controller;
class AdmController extends Controller {
	function __construct(){
		parent::__construct();
		$this->id = session('id');
		if($this->id<1){
			return $this->error('账号密码错误','/Admin/login/index');
		}


		  $this->user = D('admin')->where(array('id'=>$this->id))->find();

		if(!$this->user){
			return $this->error('账号密码无效','/Admin/login/index');
		}
	}

}

 ?>
```
<!--more-->


### 单字母函数

```php
# I函数获取用户输入
I('get.xx')；
I('post.xx')；
#U函数处理跳转路径
U('/admin/index');
#D函数实例化一个模型
$admin = D('admin');

```

页面跳转啊 从定向


```php
//  页面跳转 无需等待
return $this->redirect('/admin/auser');
//  页面跳转 有提示信息
$this->error('操作成功,成功修改'.$is.'条','/admin/auser/index');


```


