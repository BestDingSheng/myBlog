---
title: nvm安装以及使用
date: 2017-11-21 11:00:39
tags: node
---

> 在我们开发项目中经常会使用到不同版本的node 常规的安装node只能安装一种版本 所以就出现了nvm等版本切换工具


参考资料 
https://segmentfault.com/a/1190000004404505
http://bubkoo.com/2017/01/08/quick-tip-multiple-versions-node-nvm/


### 卸载全局安装的 node/npm

在官网下载的 node 安装包，运行后会自动安装在全局目录，使用过程中经常会遇到一些权限问题，所以推荐按照以下方法卸载全局安装的 node/npm。
首先，打开你 Finder，按 shift+command+G，打开前往文件夹的窗口，分别输入下列目录进去之后删除 node 和 node_modules 相关的文件和文件夹:
打开 /usr/local/lib，删除 node 和 node_modules 相关的文件和文件夹
打开 /usr/local/include，删除 node 和 node_modules 相关的文件和文件夹
如果你是使用的 brew install node 安装的 NodeJS，那么你还需要在终端中执行 brew uninstall node 命令来卸载
检查你的个人主文件夹下面的所有的 local、lib 以及 include 文件夹，并且删除所有与 node 和 node_modules 相关的文件以及文件夹
打开 /usr/local/bin 并删除 node 可执行文件

你可能还需要在你的终端中输入一些额外的指令：


```
sudo rm /usr/local/bin/npm
sudo rm /usr/local/share/man/man1/node.1
sudo rm /usr/local/lib/dtrace/node.d
sudo rm -rf ~/.npm
sudo rm -rf ~/.node-gyp
sudo rm /opt/local/bin/node
sudo rm /opt/local/include/node
sudo rm -rf /opt/local/lib/node_modules

```


### Nvm安装


```
wget -qO- https://raw.githubusercontent.com/creationix/nvm/v0.33.0/install.sh | bash

```
安装完需要添加到全局的环境变量中
执行 source ~/.zshrc  会使配置生效

### Nvm常用命令

nvm ls-remote  查看node有哪些版本 可以安装
nvm install v6.19 安装node版本
nvm ls 查看安装了哪些node版本
nvm use v6.18 切换node版本


