---
layout: post
title: "gitignore忽略不必要文件"
date: 2019-9-14 22:16:01
description: "工具"
tag: Tools
---

**忽略文件的原则是：**

+ 忽略操作系统自动生成的文件，比如缩略图等；   

+ 忽略编译生成的中间文件、可执行文件等，也就是如果一个文件是通过另一个文件自动生成的，那自动生成的文件就没必要放进版本库，比如Java编译产生的.class文件；   
+ 忽略你自己的带有敏感信息的配置文件，比如存放口令的配置文件。   

+ .gitignore文件本身要放到版本库里，并且可以对.gitignore做版本管理！

#### 1. 先在项目路径下添加.gitignore文件。
#### 2. 编辑.gitignore文件，其实就是输入一些相对路径或者通配符来避免文件提交。
   
```
.DS_Store
.idea
vendor/

```

+ 利用`git status` 查看，可以看出排除了的文件，避免了其提交。

#### 3. Github DeskTop 中添加
   
**+ ![](https://tva1.sinaimg.cn/large/006y8mN6ly1g6zf27vt98j30gl07274e.jpg)**
<br>
**+![](https://tva1.sinaimg.cn/large/006y8mN6ly1g6zf27luccj30fp0c83ym.jpg)**