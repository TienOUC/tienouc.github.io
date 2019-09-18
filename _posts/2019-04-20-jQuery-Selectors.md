---
layout: post
title: "jQuery Selectors"
date: 2019-07-07 17:00:06 
description: "工具"
tag: WEB/jQuery
---
   

### 基本选择器
1. **ID选择器**
	$('###ID')
	
2. **Element选择器**
	$('element')
	
3. **Class选择器**
	$('.className')
	
4. **通配符选择器**
	$('*')--选中所有元素，不建议使用
	
### 多项选择器
1. $("selector1,selector2,selectorN"); 将每一个选择器匹配到的元素合并后一起返回。 可以指定任意多个选择器，并将匹配到的元素合并到一个结果内。 顺序会遵循html的顺序

### 层级选择器

 1.   $('ancestor descendant')  **祖先后代选择器**  在给定的祖先元素下面匹配所有的后代元素;
		代码举例省略
	
 2.  $('parent>child')  **子选择器** 在给定的父元素下匹配所有的子元素

```
html
<body>
	<h3>必备基础</h3>
	<ul>
		<b>分类</b>
		<li>HTML</li>
		<li>CSS</li>
		<li>JavaScript</li>
		<li>jQuery</li>
	</ul>
	<h3>热门技术</h3>
	<ul>
		<b>分类</b>
		<li>vue.js</li>
		<li>es6</li>
		<li>less/sass</li>
	</ul>
	<script src="https://cdn.bootcss.com/jquery/3.3.1/jquery.js"></script>
    <script>
      $(function(){
        $('ul>li').css('color','red');
      });
    </script>
</body>
```   

![1](http://ww2.sinaimg.cn/large/006tNc79ly1g5rdd2dkjsj307r0grwee.jpg)   

3. $('prev~siblings') **兄弟选择器** 匹配pre后面所有siblings()元素;

```
html
<body>
	<h3>必备基础</h3>
	<ul>
		<b>分类</b>
		<li>HTML</li>
		<li>CSS</li>
		<li>JavaScript</li>
		<li>jQuery</li>
	</ul>
	<h3>热门技术</h3>
	<ul>
		<b>分类</b>
		<li>vue.js</li>
		<li>es6</li>
		<li>less/sass</li>
	</ul>
	<script src="https://cdn.bootcss.com/jquery/3.3.1/jquery.js"></script>
    <script>
      $(function(){
        $('b~li').css('background','green');
      });
    </script>
</body>
```   
![2](http://ww2.sinaimg.cn/large/006tNc79ly1g5rdd91vx3j308e0h60sm.jpg)   


4. $('prev+next')   **同级选择器** 匹配所有紧跟在prev元素后的next元素 *prev和next同级*   

```
html
<body>
	<h3>必备基础</h3>
	<ul>
		<b>分类</b>
		<li>HTML</li>
		<li>CSS</li>
		<li>JavaScript</li>
		<li>jQuery</li>
	</ul>
	<h3>热门技术</h3>
	<ul>
		<b>分类</b>
		<li>vue.js</li>
		<li>es6</li>
		<li>less/sass</li>
	</ul>
	<script src="https://cdn.bootcss.com/jquery/3.3.1/jquery.js"></script>
    <script>
      $(function(){
        $('ul+h3').css('color','red'); //prev和next同级
      });
    </script>
</body>
```   
   
![3](http://ww1.sinaimg.cn/large/006tNc79ly1g5rddfs0t9j308q0gtjrb.jpg)   



### 属性选择器

1. $( '[attribute]')  属性名
2. $( '[attribute=value]') 属性值
3. $( '[attribute=!value]') 非属性值
4. $( '[attribute^=value]') 匹配属性值以value开头（含有value）的所有元素。 
5. $( '[attribute\$=value]') 匹配属性值以value结尾（含有value）的所有元素。
6. $( '[attribute*=value]') 匹配属性值包含value（含有value）的所有元素。
7. $( '[selector1] [selector2]... [selectorN]')  匹配1~N的交集


### 过滤器
 1. **child**
 ：first-child:子元素的某一个标签 第一个 
 ：last-child:子元素的某一个标签 最后一个 
 ：nth-child:子元素标签 第几个 
 ：nth-last-child:子元素倒数第几个 
 ：only-child:父元素后面仅有一个标签
 
   
 
 ```

  $('x > p:first-child')	 //X下第一个标签是P标签的节点
  $('x > p:last-child') 	 //X下倒数第一个标签是P标签的节点
  $('x > p:nth-child(n)') 	 //x下第n个标签是P标签的节点
  $('x > p:nth-last-child(n)')	 //x下倒数第n个是P标签的节点
  $('x > p:only-child') 		 //x下只有一个标签是P标签的节点
 ```
 
 

2. **type**
   和child类似，child侧重找子节点，找某个元素必需满足该元素在在父节点下处于相同位置 
   type侧重节点类型，type不强调所有标签的排序，只要有该元素就可以。
    ：first-of-type:子元素的某一个标签 第一个 
    ：last-of-type:子元素的某一个标签 最后一个 
    ：nth-of-type:子元素标签 第几个 
    ：nth-last-of-type:子元素倒数第几个 
    ：only-of-type:父元素后面仅有一个标签

   ​    

   ```

   $('x > p:first-of-type')	 //X下第一个P标签节点
   $('x > p:last-of-type') 	 //X下倒数第一个P标签节点
   $('x > p:nth-of-type(n)') 	 //x下第n个P标签节点
   $('x > p:nth-last-of-type(n)')	 //x下倒数第n个P标签节点
   $('x > p:only-of-type') 		 //x下只有一个P标签的节点
   ```

      

**过滤器参数**

 - n:匹配子元素序号。必须为整数，从1开始 
 - even:匹配所有偶数元素 
 - odd:匹配所有奇数元素 
 - formual:使用特殊公式如(an+b)进行选择。


### 表单选择器

1. **表单元素**
  ![4](http://ww4.sinaimg.cn/large/006tNc79ly1g5rddoc0nyj30lu0cwt8w.jpg)

  

2. **表单状态**
  ![5](http://ww3.sinaimg.cn/large/006tNc79ly1g5rddvp06aj30mg09f3yq.jpg)


### 查找过滤

 1. .find() 搜索所有与指定表达式匹配的元素,返回所有后代（包括孩子、孙子等等后代） 
   
 2. .children() 返回所有被选元素的直接子元素，返回子元素（孩子） 
   
 3. .parent() 返回被选元素的直接父元素
 4. .next()  .prev()返回所选元素中紧邻的后面（前面）的元素集合
   
 5. .eq() 获取当前链式操作中第n(可正可负)个jQuery对象(这里索引从0开始) 
   
 6. .siblings()获得匹配集合中每个元素的同辈元素，通过选择器进行筛选是可选的
   
 7. .filter()筛选出与指定表达式匹配的元素集合。


  **参数**
 - expr:字符串值，包含供匹配当前元素集合的选择器表达式。    
 - object:现有的jQuery对象，以匹配当前的元素。   
 - element:一个用于匹配元素的BOM元素。   
 - fn:一个函数用来作为测试元素的集合。