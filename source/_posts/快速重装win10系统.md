---
title: "快速重装win10系统"
catalog: true
date: 2020-3-18 19:35:19
subtitle: 
header-img: "https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/Demo.png"
tags:
- win10
- 系统重装

---

怎么快速的给自己的电脑重装一个系统？

---

### 1、下载win镜像

---

可以在I Tell You 上下载纯净版win10镜像，[https://msdn.itellyou.cn/](https://msdn.itellyou.cn/) 

X64为64位的，X86为32位的，正常个人使电脑选择consumer editions。下面为迅雷的链接，打开迅雷就可以下载了。大家根据自己电脑情况下载相应版本。不要把镜像下载到一会要装系统的分区（桌面也是在C盘哦）！



![](https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/win镜像.png)

---

### 2、制作优盘启动工具

---

下载大白菜优盘启动盘制作工具,下载地址：[http://www.dabaicai.pw/](http://www.dabaicai.pw/) 

推荐大家下载UEFI版。下载后安装并启动大白菜，插入优盘。

![](https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/dabaicai1.png)

设备选择自己的优盘，其他默认即可。点开始制作。

![](https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/dabaicai2.png)

会删除优盘里面的文件，重要文件提前备份。稍等几分钟。制作完成后可以尝试模拟启动。

![](https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/dabaicai3.png)4

![](https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/dabaicai4.png)

优盘启动盘制作就完成了。

---

### 3、进入bios

---

重启电脑进行电脑bios。各品牌电脑进入bios的热键不太一样，大家可以百度一下自己电脑怎么进入bios。我以联想笔记本为例。联想笔记本左边有一个小孔，用针往里按一下，会有按键按下的感觉。开机时，不按电源键，按一下这个小孔就会进入bios。

进入bios，选择BIOS setup,

![](https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/bios1.jpg)

![](https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/bios2.jpg)

进入后选择Boot，修改Boot Mode为UEFI模式，之后选择Exit，选择退出并保存。

再次进入bios，选择Boot Menu，

![](https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/bios3.jpg)

![](https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/bios4.jpg)

选择从优盘启动，USB HDD。我的优盘是金士顿的。确定，大白菜优盘启动。

---

### 4、大白菜优盘启动

---

成功进入大白菜。

如果硬盘还没有安装过系统，一定要重新分一下区，使用DIskGenius工具。选择快速分区，分区类型为GUID，一定要创建ESP和MSR分区。点确定开始建立分区 。

![](https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/分区1.png)

![](https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/大白菜1.png)

点浏览，选择刚才下载的win10镜像。可以选择win10的不同版本，至于各版本有什么不同，在此不多赘述，大家可以自己搜索一下。正常家用看电影办公选择家庭的就可以。如果个人有些开发的需要，选择专业的就可以。



![](https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/大白菜2.png)

![](https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/大白菜3.png)

选择系统将要安装的位置，不要选错了！

![](https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/大白菜4.png)

选择全自动安装，其他默认即可。等待一会。

![](https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/大白菜5.png)

制作完成会提示你重启电脑，重启电脑，此时拔掉优盘。

---

### 5、win10安装设置

---



![](https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/win10安装1.png)

![](https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/win10安装2.png)

win10开始系统准备，等一会，可能需要一段时间。会重启几次。之后依次根据提示设置。



![](https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/win10安装3.png)

![](https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/win10安装 4.png)



![](https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/win10安装6.png)

![](https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/win10安装7.png)

![](https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/win10安装8.png)

有账户可以登录一下，没有就点左下的脱机账户。

![](https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/win10安装70.png)

没有账户就选择有限体验，实际上Microsoft的应用和服务咱们是不用的，有没有就无所谓了。

![](https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/win10安装10.png)

输入用户名。

![](https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/win10安装11.png)

输入登录密码。输入两次。

![](https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/win10安装12.png)

设置3个安全问题。

![](https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/win10安装13.png)

点否即可。

![](https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/win10安装14.png)

根据自己需要选择。

![](https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/win10安装15.png)

根据自己需要选择。

![](https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/win10安装20.png)

到这里，系统就装完了。



---





博客网站  ：
[ccbirds.cn](http://ccbirds.cn)   
[ccbirds.github.io](https://ccbirds.github.io/)


<head>
    ..
    <script src='//unpkg.com/valine/dist/Valine.min.js'></script>
    ...
</head>
<body>
    ...
    <div id="vcomments"></div>
    <script>
        new Valine({
            el: '#vcomments' ,
	    appId: 'vXidTKzEclYBf4IxomY5Vqo5-gzGzoHsz',
    	    appKey: 'YYe3hk4yLV5lQ3M5oO7tHE6t',
            notify:false, 
            verify:false, 
            avatar:'mp', 
            placeholder: 'ヾﾉ≧∀≦)o来啊，快活啊' 
        })
    </script>
</body>