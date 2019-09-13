---
layout: post
title: "CSS图片旋转-transform"
date: 2019-05-7 17:00:06 
description: "工具"
tag: WEB/CSS
---

```
html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
<style>
    .mainDiv{
        width:100px;
        height:100px;
        margin:100px auto;
        text-align: center;
        line-height: 100px;
        font-weight: bold;
        color:#ddd;
        background:#ddd;
        border:1px solid #ddd;
        -webkit-transform:rotate(0deg) scale(1);
        -moz-transform:rotate(0deg) scale(1);
        transform:rotate(0deg) scale(1);            //旋转0度，倍放1
        -webkit-transition:2s;                        //  动画持续时间
        -moz-transition:2s;
        transition:2s;
        
    }
    .mainDiv:hover{
       -webkit-transform:rotate(720deg) scale(2);
       -moz-transform:rotate(720deg) scale(2);
       transform:rotate(720deg) scale(2);
       color:black;
       background:red;
       box-shadow:5px 5px 5px gray;
    }
</style>
<title>css3特效</title>
</head>
<body>
<div class="mainDiv">您好</div>
</body>
</html>
```

