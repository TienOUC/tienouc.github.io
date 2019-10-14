---
layout: post
title: "Js之 toString() 和 String() 的区别"
date: 2019-07-05 19:00:00
description: ""
tag: Javascript
---
> **null, undefined 没有toString方法**
   
**举例说明** 
```
Eg1:
console.log([1,2,3,4].constructor.toString().indexOf("Array") > -1 );//
console.log(String([1,2, 3,4].constructor).indexOf("Array") > -1);  

返回
True
True

==============

Eg2:
var test = null;
var test_1;
  // String()
console.log(String(test)); 
console.log(String(test_1)); 

  // toString()
console.log(test.toString());
console.log(test_1.toString());

返回
null
undefined
TypeError: Cannot read property 'toString' of null

```   
