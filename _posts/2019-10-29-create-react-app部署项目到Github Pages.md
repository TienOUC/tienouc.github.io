---
layout: post
title: "create-react-app部署项目到Github Pages"
date: 2019-10-29 17:00:06 
description: "工具"
tag: Tools
---
[账单薄项目预览](http://willtien.com/Account-app/)   
mockAPI: [API endpoint](https://5db85da7177b350014ac796d.mockapi.io/api/v1/records)
#### **1. 创建项目**

使用 create-react-app 脚手架创建项目   

```
npm install create-react-app 
npm create-react-app my-app
cd my-app
npm start  // 运行

npm run eject //解压默认webpack包，操作不可逆
```   

   
#### **2. 将本地的文件 push 至远端仓库**   

```
git init         // 初始化一个文件夹为本地仓库
git status    // 查看状态和是否存在.git文件
git add .      // 添加到暂存区
git commit -m '提交'            // 提交到版本库且增添提交备注
git remote add origin {url}   // {url} 是你的GitHub上reponsitory地址
git push -u origin master     // 将代码推送到GitHub
```
   

#### **3. Github Pages 部署**

把项目部署成GitHub pages，在GitHub上点开项目到设置，翻到Github Pages设置处，可以看到GitHub Pages只能使用master、gh-pages分支或者master下面的docs文件夹。
这里使用的是gh-pages分支的方式来创建

#### **4. 安装 gh-pages**

```
npm install gh-pages --save-dev
```   

通过 gh-pages 中间件，可以把 build 文件下的文件推送到 GitHub，并且创建 gh-pages branch

#### **5. 修改 package.json**
```
{
    "name": "react_demo",
    "version": "1.1.0",
    "private": true,
  + "homepage": "./",  // 表示你访问的页面
},
```   

+ 注意：homepage 不要设置成 github page上生成的那个链接路径，比如https://username.github.io/react_demo/。如果设置成上面的连接，build打的包会这所有路径前面加上react_demo。比如 index.html 文件中对同等目录下的文件引用应该是 src='./index.css'，结果会变成src='./react_demo/index.css'，这样部署后肯定无法访问，所有资源都找不到。   

增加npm scripts命令，推送gh-pages
   
```
"scripts": {
        ...
  + "predeploy": "npm run build" , // 将你的项目预编译成静态文件放在build文件夹
  + "deploy": "gh-pages -d build"  // 是使用gh-pages 部署你的build文件夹下的内容
},
```
    

注意修改之后注意也 push 上去
#### **6. 推送项目**

GitHub Pages只是部署项目，react代码直接放上去是识别不了的，所以部署的是打包编译后到代码   

```npm run build```      
> **Webpack 4.X打包Bootstrap4.x失败解决办法**
```
npm install jquery --save // Bootstrap4.x 依赖JQuery，所以需要先安装JQuery
npm install popper.js --save // Bootstrap4.x 依赖Popper，所以需要先安装Popper
npm install bootstrap --save // 安装Bootstrap4.x
```   

编译后就可以推送了,执行上面配置的命令。   


```npm run deploy```      
   

这时github上项目就多出了一个gh-pages的branch，在设置中Github Pages处选择gh-pages分支保存，部署完成。
![](https://tva1.sinaimg.cn/large/006y8mN6ly1g8hni5w4moj30kf0gm0t6.jpg)   

**部署时候具体执行的操作大概为：**
1. 按照 package.json 里面增加配置代码
2. build 打包编译代码文件
3. 使用 gh-pages 工具把 build 文件下的文件推送到 GitHub部署到新的gh-pages分支上
4. 发布页面


