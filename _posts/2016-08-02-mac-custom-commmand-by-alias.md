---
layout: post
title: Mac 下自定义命令
category: mac
tags: [mac, custom command, alias]
---

## Mac 下自定义命令步骤

### 1.根目录下打开 .bash_profile

```
vim .bash_profile
```


### 2.输入 i 进入编辑

```
alias '自定义命令名称'='命令'
// 如：
alias l='ls'
```

### 3.保存并退出

```
esc
:wq
```

### 4.激活 .bash_profile

```
source .bash_profile
```

### 5.成功

---

### 参考连接

- [苹果系统或Linux系统设置快捷命令别名alias](http://jingyan.baidu.com/article/d45ad148e801c769552b800c.html)
- [linux/mac下的自定义命令alias，并保存别名使其永久生效（重启不会失效）](http://blog.csdn.net/jianglei421/article/details/8510723)
- [ vim打开文档和多文档编辑](http://blog.csdn.net/huiguixian/article/details/6231425)
