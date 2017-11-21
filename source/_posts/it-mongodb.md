---
title: mongodb使用
date: 2017-08-25 09:49:08
tags: [node,后台]
---


### 安装

官网 https://www.mongodb.com/
手册 https://docs.mongodb.org/manual/

mac 安装

```shell
brew install mongodb
```

### 开机
```shell
mongod --dbpath path #开机
mongo #使用
mongoimport #导入
```

### 操作命令
* show dbs // 列出所有数据库
* use 数据库名字 // 使用数据库 没有就自动新建
* db 查看当前所在数据库
* db.student.insert({'namae':'dingsheng'}) // 插入数据 没有student 这个集合就自动新建
* show collections // 查看数据库集合
* db.dropDatabase() // 删除当前所在数据库 


