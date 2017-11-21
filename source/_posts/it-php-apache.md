---
title: 阿里云web服务器环境配置
date: 2017-06-29 09:27:15
tags: [php,后台]
---

第一次买服务器倒腾了半天才把web服务器FTP配置好
阿里云服务器可以随意更换系统 一开始买的是linux系统 ，由于没接触过 然后吧系统换成 windos的了 

### web服务器搭建

在服务器里我用的xampp这个集成环境 百度搜下 直接下载就可以了 直接下一步下一步 傻瓜试的安装
apache默认用的80端口 
mysql默认用的3306端口
<!--more-->

在服务器本地通过localhost就直接能访问到了，但是我在我自己的电脑通过公网ip访问不到 ，打客服电话得知须要在阿里云上开通80端口的访问权限 
其他的同理 须要开通对外访问端口 80 3306 21 等
![](http://oo0pbw6u4.bkt.clouddn.com/WX20170628-093533@2x.png)


### Ftp安装
xampp里面集成了ftp只需要添加用户名，和设置用户权限就可以了
![](http://oo0pbw6u4.bkt.clouddn.com/fpt1.png)
![](http://oo0pbw6u4.bkt.clouddn.com/ftp2.png)
![](http://oo0pbw6u4.bkt.clouddn.com/ftp3.png)
![](http://oo0pbw6u4.bkt.clouddn.com/ftp4.png)
配置完以后阿里云服务器本地可以使用ftp了 但是我通过公网还是访问不了然后就各种百度
在windos里面需要在防火墙里面设置
[请看这篇文章](https://jingyan.baidu.com/article/0eb457e50b1ad003f1a905de.html?from=timeline&isappinstalled=1)

