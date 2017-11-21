---
title: Mac Mamp 多站点配置
date: 2017-06-29 16:23:30
tags: mac
---

### MAMP配置多虚拟主机
一：在终端输入  

```shell
vim /Applications/MAMP/conf/apache/httpd.conf  
```
搜索httpd-vhosts.conf 找到：#Include  /Applications/MAMP/conf/apache/extra/httpd-vhosts.conf 将#去掉，使虚拟地址的配置文件生效。

二：vim /Applications/MAMP/conf/apache/extra/httpd-vhosts.conf，在配置文件最后加入需要配置的虚拟主机配置

<!--more-->

```conf
#配置test.com
<VirtualHost *:80>
    ServerAdmin test.com
    DocumentRoot "/Applications/MAMP/htdocs/test"
    ServerName test.com
    ServerAlias test.com
    ErrorLog "logs/test.com-error_log"
    CustomLog "logs/test.com-access_log" common
</VirtualHost>
```

```conf
#配置active.com
<VirtualHost *:80>
    ServerAdmin active.com
    DocumentRoot "/Applications/MAMP/htdocs/active/"
    ServerName active.com
    ServerAlias active.com
    ErrorLog "logs/active.com-error_log"
    CustomLog "logs/active.com-access_log" common
</VirtualHost>
```
三：进入hosts 文件 vim /etc/hosts
加入
127.0.0.1  test.com
127.0.0.1   active.com 
重启appache服务器，打开浏览器输入test.com 和activie.com即可访问对应网站



[原文地址](http://blog.csdn.net/sinat_14826983/article/details/50630071)


