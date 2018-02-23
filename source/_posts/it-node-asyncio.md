---
title: node处理高并发异步io理解
date: 2018-02-02 15:35:39
tags: node
---

I/O是什么 input/out读写，异步io是什么就是异步去操作读取文件发送ajax请求都算异步io

为什么说nodejs擅长高并发io ，因为node EventLoop事件循环机制

为什么nodejs不擅长cpu密集型操作。因为异步任务要等同步任务执行结束如果cpu密集型计算太久会阻塞异步操作

```js
// 这就是一个cpu密集型的操作
for (let i = 0; i < 1000000; i++) {
    console.log(i);
}
```

### 参考资料

http://www.cnblogs.com/dudeyouth/p/6698274.html


