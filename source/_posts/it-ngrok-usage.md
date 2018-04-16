---
title: ngrok使用笔记
date: 2018-04-16 16:50:12
tags: node
---

> 有时候我们需要把我们本地的服务让外面访问,那么这个时候我们就可以使用 ngrok 使用简单 暴力 还能生成https 服务


”I want to expose a local server behind a NAT or firewall to the internet.”

![](https://camo.githubusercontent.com/f2d698991e6a0411680413ebcc15a6460b8beda3/68747470733a2f2f6e67726f6b2e636f6d2f7374617469632f696d672f6f766572766965772e706e67)

### 什么是ngrok

ngrok是一个反向代理，用于创建从公共端点到本地运行的Web服务的安全隧道。
ngrok捕获并分析隧道上的所有流量，以供日后检查和重播。

### github

https://github.com/inconshreveable/ngrok

star 1.3k 

<!--more-->

### 使用

官网下载  把下载的ngrok放在项目目录

./ngrok http 8080 就能代理本地8080端口

运行成功后会显示下面的界面

```
ngrok by @inconshreveable                                       (Ctrl+C to quit)

Session Status                online
Session Expires               7 hours, 59 minutes
Version                       2.2.8
Region                        United States (us)
Web Interface                 http://127.0.0.1:4040
Forwarding                    http://ab6f37b7.ngrok.io -> localhost:8080
Forwarding                    https://ab6f37b7.ngrok.io -> localhost:8080

Connections                   ttl     opn     rt1     rt5     p50     p90
                              0       0       0.00    0.00    0.00    0.00
```
