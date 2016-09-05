---
layout: post
title: NPM 常用使用命令
category: npm command
tags: [npm, command, start]
---

## NPM 常用使用命令
---

> 写在前面

NPM（node package manager）：node 包管理

```<>``` - 必填字段 

```[]``` - 可选字段

> 目标

将开发者从繁琐的包管理工作（版本、依赖等）中解放出来，更加专注于功能的开发。

> 安装

1.安装NodeJS

2.sudo

3.node -v

4.npm -v

> 场景

1.允许用户从NPM服务器下载别人编写的第三方包到本地使用。

2.允许用户从NPM服务器下载并安装别人编写的命令行程序到本地使用。

3.允许用户将自己编写的包或命令行程序上传到NPM服务器供别人使用。

---

### npm 模块引用

#### npm 安装模块
```
$ npm install <package>[@version]
```

如果出现错误：
```
npm err! Error: connect ECONNREFUSED 127.0.0.1:8087 
```

解决办法为：

```
$ npm config set proxy null
```

在package.json所在目录下使用npm install . -g可先在本地安装当前命令行程序，可用于发布前的本地测试。


/        | 本地安装 | 全局安装
---      | ---                    | ---
命令      | npm install <package>  | npm install <package> -g
安装目录  | ./node_modules         | user/local/node_modules 或 node安装目录下/node_modules
引用      | 直接require            | 直接在命令行

###### 例子：babel-cli
---

#### npm 创建全局链接(不支持windows)
```
$ npm link <package>
```
---

#### npm 列出所有安装模块
```
$ npm ls [-g]
```

#### npm 查看模块\[简\](输出安装目录和版本)
```
$ npm ls <package>
```

#### npm 查看模块\[繁\](输出package.json)
```
$ npm info <package>
```

#### npm 更新模块
```
$ npm update <package>
```

#### npm 卸载模块
```
$ npm uninstall <package>[@version]
```

#### npm 搜索模块
```
$ npm search <package>
```
---

### npm 模块创建

#### npm 创建模块
```
$ npm init
```

#### npm 资源库中注册用户（使用邮箱注册）
```
$ npm adduser
Username: xxxx
Password:
Email: (this IS public) xxx@xxx.com
```

#### npm 发布模块
```
$ npm publish
```

#### npm 撤销发布模块
```
$ npm unpublish <package>@<version>
```
---

### npm proxy相关

#### npm 设置proxy
```
$ npm [config] set proxy http://proxy.example.com:8080
```

#### npm 查看proxy
```
$ npm [config] get proxy
```

#### npm 删除proxy
```
$ npm delete proxy
```

#### npm 查看配置
```
$ npm config list
```

#### npm 修改配置
```
$ npm config edit
```
---

### npm help

#### npm 查看所有命令
```
$ npm help
```

#### npm 查看某条命令
```
$ npm help <command>
$ npm <command> --help
```

#### npm 清除缓存(用于对付使用相同版本号发布新版本代码的人)
```
$ npm cache clear
```
---

### 版本号
使用NPM下载和发布代码时都会接触到版本号。NPM使用语义版本号来管理代码，这里简单介绍一下。

语义版本号分为X.Y.Z三位，分别代表主版本号、次版本号和补丁版本号。当代码变更时，版本号按以下原则更新。

1.如果只是修复bug，需要更新Z位。

2.如果是新增了功能，但是向下兼容，需要更新Y位。

3.如果有大变动，向下不兼容，需要更新X位。
  
版本号有了这个保证后，在申明第三方包依赖时，除了可依赖于一个固定版本号外，还可依赖于某个范围的版本号。例如"argv": "0.0.x"表示依赖于0.0.x系列的最新版argv。
NPM支持的所有版本号范围指定方式可以查看官方文档。

> 常见版本声明形式

-"~1.2.3" = ">=1.2.3 <1.3.0"

-"~1.2" = ">=1.2.0 <1.3.0"

-"~1" = ">=1.0.0 <1.1.0"

1."1.2.x" = ">=1.2.0 <1.3.0"

2."1.x.x" = ">=1.0.0 <2.0.0"

3."1.2" = "1.2.x"

4."1.x" = "1.x.x"

5."1" = "1.x.x"

> 版本书写要求

1.版本可以v开头，比如 v1.0.1（v只是可选）

2.1.0.1-7，这里的7是所谓的“构建版本号”，不理是神马，反正版本大于1.0.1

3.1.0.1beta，或者1.0.1-beta，如果1.0.1后面不是 “连字符加数字” 这种形式，那么它是pre release 版本，即版本小于 1.0.1

4.根据b、c，有：0.1.2-7 > 0.1.2-7-beta > 0.1.2-6 > 0.1.2 > 0.1.2beta

---

### Package.json 属性说明
1.name - 包名。

2.version - 包的版本号。

3.description - 包的描述。

4.homepage - 包的官网 url 。

5.author - 包的作者姓名。

6.contributors - 包的其他贡献者姓名。

7.repository - 包代码存放的地方的类型，可以是 git 或 svn，git 可在 Github 上。

8.main - main 字段是一个模块ID，它是一个指向你程序的主要项目。就是说，如果你包的名字叫 express，然后用户安装它，然后require("express")。

9.keywords - 关键字

10.dependencies - package的应用依赖模块，即别人要使用这个package，至少需要安装哪些东东。应用依赖模块会安装到当前模块的node_modules目录下。

11.devDependencies - package的开发依赖模块，即别人要在这个package上进行开发。

---

### 参考资料：
- [NPM 使用介绍](http://www.runoob.com/nodejs/nodejs-npm.html)
- [NPM小结 - 程序猿小卡](http://www.tuicool.com/articles/VB7nYn)
- [npm link 命令解析](http://www.tuicool.com/articles/7B7Jfm)


