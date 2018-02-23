---
title: Liunx文件传输Scp命令使用
date: 2017-11-22 10:50:04
tags: linux
---

> linux上面本地和服务器如何进行文件传输---scp 
> linux 的 scp 命令 可以 在 linux 之间复制 文件 和 目录； 
>


### 文件上传几种方式

* scp local_file remote_username@remote_ip:remote_folder 
* scp local_file remote_username@remote_ip:remote_file 
* scp local_file remote_ip:remote_folder 
* scp local_file remote_ip:remote_file 

列子
<!--more-->

* scp /home/space/music/1.mp3 root@www.cumt.edu.cn:/home/root/others/music 
*  scp /home/space/music/1.mp3 root@www.cumt.edu.cn:/home/root/others/music/001.mp3 
*  scp /home/space/music/1.mp3 www.cumt.edu.cn:/home/root/others/music 
* scp /home/space/music/1.mp3 www.cumt.edu.cn:/home/root/others/music/001.mp3 


### 文件夹上传

需要在scp上面加 -r
列如

* scp -r /home/space/music/ root@www.cumt.edu.cn:/home/root/others/ 
* scp -r /home/space/music/ www.cumt.edu.cn:/home/root/others/ 



