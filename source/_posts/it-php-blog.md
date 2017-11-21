---
title: php+mysql 搭建简易博客笔记
date: 2017-06-16 07:07:35
tags: [php,后台]
---

1 封装个db类把数据库连接放到类里

```php
<?php 

class db{
	function __construct(){
		$this->mysqli = new mysqli('localhost', 'root', 'root', 'blog');

		if( $this->mysqli->connect_errno > 0 ){
			echo "连接错误";
			echo $this->mysqli->connect_error;
			exit;
		}
		$this->query("SET NAMES UTF8");
	}

	function query($sql){
		return $this->mysqli->query($sql);

	}
}


?>
```
<!--more-->
    
2 封装input类 获取get post session 值


```php
<?php 

class input{

	function get($key = false){
		if($key===false){
			return $_GET;
		}
		if(isset($_GET[$key])){
			return $_GET[$key];
		}else{
			return false;
		}
	}
	function post($key = false){
		if($key===false){
			return $_POST;
		}
		if(isset($_POST[$key])){
			return $_POST[$key];
		}else{
			return false;
		}
	}	
	function session($key=false){
		if($key===false){
			return $_SESSION;
		}
		if(isset($_SESSION[$key])){
			return $_SESSION[$key];
		}else{
			return false;
		}
	}
}
?>

```
3 config 


```php
<?php 

//  程序的配置文件 
define("PATH", dirname(__FILE__));
include(PATH . "/core/db.php");
$db = new db();

include(PATH . "/core/input.class.php");
$input = new input();


 ?>
```





