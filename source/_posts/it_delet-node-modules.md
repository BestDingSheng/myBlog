---
title: windows如何快速删除node_modules
date: 2017-04-05 11:29:44
tags: [环境]
---
> 之前用windows电脑做依赖node项目的时候总是会碰到删除node modules文件夹困难，下面教大家如何简单暴力快速的删除node_modules文件夹

**来跟着我左手右手一个慢动作**

1.首先全局安装rimraf插件

```bash
npm install rimraf -g
```
<!--more-->
2.在项目根目录执行一下命令

```bash
rimraf node_modules
```

**就这么简单是不是很暴力**


-------


<div  align=center>
    <center> 扫描二维码添加丁盛为你的好友</center ><center><font color=#f75000 size=>技术、户外、摄影、自驾 欢迎交流</font><center><img width='40%' align='center' src='/uploads/wechat-qcode.jpg
'>
</div>




