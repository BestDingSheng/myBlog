---
title: github ssh配置
date: 2018-03-14 09:02:55
tags: [git,github]
---

1 先看本地是否有ssh文件


```
> cd ~/.ssh
> ls
id_rsa          id_rsa.pub      known_hosts

```

没有的话生成公钥和私钥


2 有则把公钥加到github


```
>cat id_rsa.pub
ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDVRgHi3gPdBcQ... xxxx@163.com
```

<!-- more -->

3 github 添加公钥示意图

![](http://our9i4zgx.bkt.clouddn.com/Snip20171220_3.png)
![](http://our9i4zgx.bkt.clouddn.com/Snip20171220_4.png)
![](http://our9i4zgx.bkt.clouddn.com/Snip20171220_5.png)

4 如果以上操作问题还不能解决,并且执行 ssh -T git@github.com 出现如下提示，说明本地公钥没有问题，则看第5步


```
> ssh -T git@github.com
Hi youcanping! You've successfully authenticated, but GitHub does not provide shell access.

```

5 看本地的.git/config设置的仓库url地址和github使用的链接地址是否一致如下图,如use https,则url需要用https的仓库地址，我的就是这个问题。

![](http://our9i4zgx.bkt.clouddn.com/blog/Snip20171226_12.png)



```
> cat .git/config
[core]
        repositoryformatversion = 0
        filemode = true
        bare = false
        logallrefupdates = true
        ignorecase = true
        precomposeunicode = true
[remote "origin"]
        url = https://github.com/youcanping/MyBlog.git
        fetch = +refs/heads/*:refs/remotes/origin/*
[branch "master"]
        remote = origin
        merge = refs/heads/master
```

6 把公钥放到系统里[最佳答案]


```
> ssh-add ~/.ssh/id_rsa
> Identity added: /Users/youcanping/.ssh/id_rsa (/Users/youcanping/.ssh/id_rsa)
```
