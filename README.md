# Tien
我的个人博客主页 &rarr;[Tien](https://willtien.com)


### 1. 如何部署

#### 1.1 安装Jekyll

>* Jekyll (支持 Mac 、Windows、ubuntu 、Linux 操作系统)                     
>* Jekyll 依赖：Ruby、bundler

参考资料:
- [Jekyll中文官方文档](http://jekyll.bootcss.com/) ， 如果你已经安装过了 Jekyll ，可以忽略此步骤。

`$ gem install jekyll`

#### 1.2 获取模板

` $ git clone https://github.com/TienOUC/tienouc.github.io.git`

#### 1.3 必要修改

在你的github里创建一个username.github.io的仓库，username指你的github用户名。      
创建完成后，把clone的模板使用git push到你的username.github.io仓库下即可。

参考资料:
- [Jekyll搭建个人博客](http://baixin.io/2016/10/jekyll_tutorials1/)  :  使用Jekyll搭建个人博客的教程，以及如何把博客模板修改成你自己的博客，里面也有大量的评论及 Jekyll 搭建博客出现过的问题。

***提示***
>* 修改 _config.yml 文件里面的内容为你自己的个人信息。
>* 如果你想使用我的模板，请把 _posts/ 目录下的文章都去掉。


#### 1.4 本地预览
进本地username.github.io/ 目录下， 开启服务 

` $ jekyll server watch`   

在浏览器输入 [127.0.0.1:4000](127.0.0.1:4000) ， 就可以看到博客即时修改后的效果了。



### 2. 效果预览

#### 2.1 博客首页   

**![首页](/images/readme//img1.jpg)**

#### 2.2 文章详情   

**![文章列表](/images/readme//img2.jpg)** 

**![文章头部](/images/readme//img3.jpg)**

**![文章尾部](/images/readme//img4.jpg)**



#### 3. 感谢        

本博客是在[Vno Jekyll](https://github.com/onevcat/vno-jekyll)基础上修改的。  

