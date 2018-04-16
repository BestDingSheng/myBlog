---
title: centos7安装epel源
date: 2018-04-15 17:33:40
tags: node
---

>EPEL 是yum的一个软件源,里面包含了许多基本源里没有的软件了，但在我们在使用epel时是需要安装它才可以了，EPEL，即Extra Packages for Enterprise Linux的简称，是为企业级Linux提供的一组高质量的额外软件包，包括但不限于Red Hat Enterprise Linux (RHEL), CentOS and Scientific Linux (SL), Oracle Enterprise Linux (OEL)，使用docker之前安装EPEL源。


### 安装 

```
yum install epel-release
```

### 查看并更新源

**查看**
```
ll /etc/yum.repos.d/
```
两个epel的repo文件:

```
epel.repo
epel-testing.repo
```
接下来就更新源：

```
yum clean all && yum makecache
```
更新成功之后就可以使用EPEL安装应用了。


### 参考资料

https://blog.csdn.net/w670328683/article/details/51673757
