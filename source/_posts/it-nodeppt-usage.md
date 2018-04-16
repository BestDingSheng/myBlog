---
title: nodeppt使用笔记
date: 2018-04-16 16:09:15
tags: node
---

> 在github上面看到一个nodejs开发的幻灯片制作的js库，简单的使用了下,发现还是挺强大的；

### 官网

https://github.com/ksky521/nodeppt  github star目前4.8k

文档写的还算详细 

<!--more-->

### 如何使用 

安装

```
npm install -g nodeppt
```
安装成功后就可以在命令行中使用 nodeppt命令 ，让我们查看nodeppt 有哪些功能

```
➜  myBlog git:(master) ✗ nodeppt --help

  Usage: nodeppt [options] [command]

  Options:

    -V, --version               output the version number
    -h, --help                  output usage information

  Commands:

    create|new [options]        create a slide
    generate|release [options]  export html file
    start [options]             start local sever show slide
    pdf                         export pdf file. Deprecated
```

- create | new 创建一个幻灯片
- generate | release 把幻灯片生成为html文件
- start 本地启动一个服务

最后一个命令已经被废弃 主要就是使用上面这个三个命令 是不是很简单呢

---

更详细的api可以看官网readme


