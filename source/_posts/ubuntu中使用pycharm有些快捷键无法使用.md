---
title: ubuntu中使用pycharm有些快捷键无法使用
date: 2020-02-27 08:57:49
catalog: true
subtitle:
tags: 
- ubuntu
- python
- pcharm
categories:
- 经验分享
---

问题描述：在使用pycharm过程中，ctrl+c,ctrl+v,ctrl+d等快捷键无法使用。

解决办法：file->setting->Editor下面有一个Vim Emulation选项。
<!--more-->
![](https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/pycharm.png)
将Handler一列中的vim全部改为IDE，点Apply。

![](https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/pycharm2.png)
这样，快捷键就可以正常使用啦。

博客网站  ：
[ccbirds.cn](http://ccbirds.cn)   
[ccbirds.github.io](https://ccbirds.github.io/)



