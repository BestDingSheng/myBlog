---
title: linux免密登陆
date: 2018-02-07 11:04:50
tags: linxu
---

> 思路：在本地生成公钥和私钥，然后将公钥放到linux的root（也就是~）目录下的.ssh文件夹下（隐藏文件夹），如何没有则生成一个。 
> 


**1 在Mac客户端命令行生成公钥和私钥**

cd ~/.ssh
ssh-keygen -t rsa

之后回车两次，注：（Enter passphrase (empty for no passphrase): 可以设置密码），免密做好后首次登录要求输入一次密码，就输入这里的密码。

生成两个文件id_rsa（私钥）和id_rsa.pub（公钥）

<!-- more -->

**2 发送公钥到CentOS服务器端**

scp id_rsa.pub user@ip:~/.ssh
如果服务器上没有.ssh文件夹，则登录服务器输入如下命令创建
mkdir ~/.ssh
chmod 700 ~/.ssh


**3 登陆CentOS服务器端,设置公钥文**

ssh user@ip casino online 注：此时还是需要输入密码
cd ~/.ssh
cat id_rsa.pub >> authorized_keys
chmod 600 authorized_keys 注：必须设置成600

### 设置别名

首先在自己的电脑上解析别名比如ding
mac环境下 host在 /etc/hosts

```
➜  /etc cat hosts
##
# Host Database
#
# localhost is used to configure the loopback interface
# when the system is booting.  Do not change this entry.
##
127.0.0.1	localhost
255.255.255.255	broadcasthost
::1             localhost
192.30.253.113 github.com
127.0.0.1  test.com
47.95.235.183 ding
```

然后连接到远程服务器在 ~/.ssh/ 目录下创建 config 文件


```
[root@iz2ze17rrh39kqzngcg4jaz .ssh]# cat config

Host ding
   User root
   HostName 47.95.235.183
   IdentityFile ~/.ssh/id_rsa.pub
   Protocol 2
   Compression yes
   ServerAliveInterval 60
   ServerAliveCountMax 20
   LogLevel INFO
```

配置好直接执行  ssh root@ding 就能直接连接了

注释： 
HostName 指定登录的主机名或IP地址 
Port 指定登录的端口号 
User 登录用户名 
IdentityFile 登录的公钥文件 
IdentitiesOnly 只接受SSH key 登录


### 参考资料

http://blog.csdn.net/superbfly/article/details/66970114

