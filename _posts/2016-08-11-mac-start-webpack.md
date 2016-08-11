---
layout: post
title: Mac 下启动 webpack 错误解决
category: mac
tags: [mac, webpack]
---

## Mac 下启动 webpack / webpack-dev-server 错误

> 在终端直接运行 **webpack** 或 **webpack-dev-server** 出错

*报错信息* 如下：

```
webpack: command not found

webpack-dev-server: command not found
```

但是我明明已经安装了呀！！！

---

### 解决方法如下：

### 1. 在 package.json 文件自定义命令

如下：


```
"scripts": {
    "compile": "cd react && webpack",
    "start": "cd react && webpack-dev-server --progress --colors"
},
```

### 2. 然后运行如下命令

即可：

```
npm run compile
npm run start
```