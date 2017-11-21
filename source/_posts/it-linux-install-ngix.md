---
title: CentOS 7 用 yum 安装 Nginx
date: 2017-09-15 14:20:18
tags: [linux,后台]
---


在 CentOS 7 中，直接使用 yum 安装 Nignx 会提示无下载源。因此，需要添加 Nginx 的下载源到 yum：

```
sudo rpm -Uvh http://nginx.org/packages/centos/7/noarch/RPMS/nginx-release-centos-7-0.el7.ngx.noarch.rpm
```
指定了下载源后，就可以使用 yum 命令来安装 Nginx 了：

```
sudo yum install -y nginx
```
安装完成的 Nginx 并不会立刻启动，需要我们手动执行命令来开启它:

```
sudo systemctl start nginx.service
```
还可以输入以下命令，让 Nginx 可以随系统自动启动：

<!--more-->

```
sudo systemctl enable nginx
```
接下来打开浏览器，访问本地地址 http://localhost 就可以看到 Nginx 的欢迎页面了~

![](http://chaishiwei.com/blog/wp-content/uploads/2017/05/201705091.png)

也可以在服务器上输入下面的命令，来查看 Nginx 所在服务器的公共IP地址，然后在客户端浏览器上输入 IP 也是可以访问的:

```
ip addr
```
相关补充：

```shell
# 开启 Nginx
service nginx start
# 停止 Nginx
service nginx stop
# 重启 Nginx
service nginx restart
# 查看 Nginx 状态
service nginx status
```
Nginx 的默认站点根目录为

```
/usr/share/nginx/html/
```
默认站点配置在

```
/etc/nginx/conf.d/default.conf
```
Nginx 主配置如下

```
/etc/nginx/nginx.conf
```
在这个配置文件里，会用到include指令，其它地方的配置文件会包含到这个主要的配置文件里，用这种方法可以让配置文件更有条理，也更容易维护。


[原文地址](http://chaishiwei.com/blog/1281.html)



-------

<div  align=center>
    <center> 扫描二维码添加丁盛为你的好友</center ><center><font color=#f75000 size=>技术、户外、摄影、自驾 欢迎交流</font><center><img width='40%' align='center' src='/uploads/wechat-qcode.jpg
'>
</div>

