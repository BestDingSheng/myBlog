---
title: CentOS 7 用 yum 安装 Mysql
date: 2017-09-16 14:20:18
tags: [linux,后台]
---

Step1: 检测系统是否自带安装mysql

```
# yum list installed | grep mysql
```
Step2: 删除系统自带的mysql及其依赖
命令：

```
# yum -y remove mysql-libs.x86_64
```
Step3: 给CentOS添加rpm源，并且选择较新的源
命令：

<!--more-->

```
# wget dev.mysql.com/get/mysql-community-release-el6-5.noarch.rpm
# yum localinstall mysql-community-release-el6-5.noarch.rpm
# yum repolist all | grep mysql
# yum-config-manager --disable mysql55-community
# yum-config-manager --disable mysql56-community
# yum-config-manager --enable mysql57-community-dmr
# yum repolist enabled | grep mysql
```
Step4:安装mysql 服务器
命令：

```
# yum install mysql-community-server
```
Step5: 启动mysql
命令:

```
# service mysqld start
```
Step6: 查看mysql是否自启动,并且设置开启自启动
命令:

```
# chkconfig --list | grep mysqld
# chkconfig mysqld on
```
Step7: mysql安全设置
命令：

```
# mysql_secure_installation
```






-------

<div  align=center>
    <center> 扫描二维码添加丁盛为你的好友</center ><center><font color=#f75000 size=>技术、户外、摄影、自驾 欢迎交流</font><center><img width='40%' align='center' src='/uploads/wechat-qcode.jpg
'>
</div>

