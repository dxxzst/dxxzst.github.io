title: 在GitHub上用HEXO搭建个人博客
tags:
  - 'HEXO '
  - 博客
  - GitHub
categories:
  - 网站技术
author: XSong
date: 2017-02-11 09:35:00
---
# 在GitHub上用HEXO搭建个人博客


----------

下面我简单概述一下, 这个博客搭建的过程以及原理。在大体上博客的整体搭建总共可以分3个部分：

> * HEXO框架的本地设置以及搭建 
> * 将网站部署到Github Pages, 以实现数据的承载. 
> * 购买域名并与绑定

<!-- more -->

## 接下来我把博客搭建的查阅网站以及博客附给大家, 可以按照我一下链接的顺序, 顺次查阅并实践. 

### 1. 博客搭建 
推荐大家看一下这篇文章：
[知行合一 | 用 Hexo 搭建博客 | Grok](http://lowrank.science/Hexo-Github/)

提醒大家, 在部署的时候最好一直使用当前博客创建路径进行部署, 例如我的博客本地路径为: D:\blog\TheKiteRunners.github.io. 那么在输入任何命令时我都会先将位置定在这里. 
或者在安装完Git后, 手动点击图标切换到该文件夹, 然后点击右键git bash here

我想大家在这篇博客中肯定会出错很多地方, 下面我把一些可能出错问题以及解决方案附上:
> * 问题1: 
第一步npm install -g hexo-cli 下载时卡住了怎么办? 
答: 有两种解决办法: 
(1.) 在每次下载时切换镜像: 输入下面命令 
npm config set registry "https://registry.npm.taobao.org" 
(2.)(推荐)直接将淘宝镜像安装下来` 
npm install -g cnpm –registry=https://registry.npm.taobao.org

> * 问题2:
使用localhost:4000访问本地blog一直无响应 
答: 可能是当前本地端口被占用了, 可以更换当前端口地址, git中输入$ hexo server -p 5000 , 然后输入localhost:5000, 再试一试. (我当时犯了一个特别愚蠢的问题….. 当我hexo server之后, 它提示我要按crtl+c…..我就按了没看到后面的to stop……小伙伴们在host server之后就直接测试localhost:4000….测试完之后再crtl+c)

### 2. 博客编辑
相信大家要是看到这里估计hexo框架已经搭建完成了, 想要去拿一篇博客测试测试, 可是小白们注意, hexo框架内置的是markdown编辑器, 不会的小伙伴们可以到这个博客里学习:
[Hexo在Github中搭建博客系统(5)Markdown语法](http://blog.csdn.net/chwshuang/article/details/52350551)

### 3. 博客主题
我用的是Next主题, 下面的Next开发文档说的很详细我就不仔细叙述了. 
[NexT 使用文档 ](https://github.com/iissnan/hexo-theme-next)

----------

**网站优化, 以及配置持续更新, 有任何新的内容都会通过这里给大家分享出来**
