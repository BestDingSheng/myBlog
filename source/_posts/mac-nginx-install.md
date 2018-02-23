---
title: 基础mac环境的nginx学习笔记
date: 2018-01-26 10:32:33
tags: mac
---

>现在是一个大前端的时代nginx这些必学不可下面是的一些安装使用时记录的笔记
>

### 安装


```bash
brew install nginx 
```

### 命令使用
启动 nginx
查看语法 nginx -t
重启 nginx -s reload
暂停 nginx -s stop

<!-- more -->

### 配置
安装完查看nginx安装在哪里 
brew info nginx 


```bash
➜  blog git:(master) ✗ brew info nginx
nginx: stable 1.12.2 (bottled), devel 1.13.8, HEAD
HTTP(S) server and reverse proxy, and IMAP/POP3 proxy server
https://nginx.org/
/usr/local/Cellar/nginx/1.12.2_1 (23 files, 1MB) *
  Poured from bottle on 2018-01-24 at 15:29:39
From: https://github.com/Homebrew/homebrew-core/blob/master/Formula/nginx.rb
==> Dependencies
Required: openssl ✔, pcre ✔
Optional: passenger ✘
==> Options
--with-debug
	Compile with support for debug log
--with-gunzip
	Compile with support for gunzip module
--with-passenger
	Compile with support for Phusion Passenger module
--with-webdav
	Compile with support for WebDAV module
--devel
	Install development version 1.13.8
--HEAD
	Install HEAD version
==> Caveats
Docroot is: /usr/local/var/www

The default port has been set in /usr/local/etc/nginx/nginx.conf to 8080 so that
nginx can run without sudo.

nginx will load all files in /usr/local/etc/nginx/servers/.

To have launchd start nginx now and restart at login:
  brew services start nginx
Or, if you don't want/need a background service you can just run:
  nginx
➜  blog git:(master) ✗ 

```
一般是在 下面这个路径下
/usr/local/etc/nginx/nginx.conf 
修改配置的话只需要修改nginx.conf 这个配置就行了

### nginx反向代理

 upstream模块放在http里面 server外面
  
    upstream hah {
        server api.douban.com;
      }
      
     server {
         location / {
            proxy_pass http://hah;
            #root   html;
            #index  index.html index.htm;
        }
     }


