---
title: linux学习笔记
date: 2018-02-07 10:12:06
tags: linux
---

项目上线部署少不了服务器,现在的一般服务器都是linux的与我们平时接触到的window大不相同,所以linux还是需要多多了解

### linux是什么
linux只是一个内核 https://www.kernel.org/

linux的发行版有很多常用的有 乌班图 和 centos

一般服务器大多都是使用的centos
<!-- more -->
[centos 官网](https://www.centos.org/)

[乌班图官网](https://www.ubuntu.com/index_kylin)

### 常用操作



**远程连接服务器**

ssh命令

**上传或者下载文件**

scp命令

**查看进程**
ps aux |grep node

**查看端口是否被占用**

ss -an -p | grep 80

lsof -i tcp:8081

**杀死进程**

kill -9 pid

**防火墙相关操作**

systemctl status firewalld

systemctl start firewalld

systemctl stop firewalld





