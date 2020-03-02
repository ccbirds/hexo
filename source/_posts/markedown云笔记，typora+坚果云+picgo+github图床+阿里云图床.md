---
title: "markedown云笔记，typora+坚果云+picgo+github图床+阿里云图床"
catalog: true
date: 2020-03-01 14:51:24
subtitle: 
header-img: "https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/Demo.png"
tags:
- 图床
- typroa
- picgo 
- github 图床
- 坚果云
- 云笔记
---


平时在弄一些东西想记一些笔记，要不等弄完也就弄完了，几乎忘了怎么弄的，最好用笔记记录一下。首先尝试了一下印象笔记，免费用户可以两个设备同步，每个月还有流量限制，主要是照片比较多，一个月的流量很可能不来够，果断放弃。

考虑用markdown来记录一些东西，因为写博客也是用的markdown，写点代码什么的比较方便。上网搜了一下，使用typroa和坚果云可以实现云同步。typroa界面十分简洁清爽，非常舒服。坚果云的空间没有其他网盘大，但主打的是同步，每个月有1G的上传和3G的下载，对于只是同步 一下md文档，完全够用了。可是又有一个新的问题。图片怎么办？对于我这个时不时就截图的人来说，这个问题很致命。很巧typroa支持使用picgo上传图片。picgo是一个上传图片到图床的一个软件。图床的选择，免费的是Github，不过毕竟是免费的，大家都懂，七牛云，据说用的比较多，不过因为域名只能用一段时间，这后就需要使用自己备案过的域名，感觉不方便，所以考虑到阿里云和腾讯云，比较了一下，价钱的话差不多，实际上都用不了多少钱。个人感觉阿里云做的比较好。所以使用typora+坚果云+picgo+github图床+阿里云图床。这样即解决了笔记问题也解决了博客图床的问题。

最重要的是typroa、坚果云、picgo都是支持windows macos 和linux。

下面以windows为例介绍一下。

---

### typroa

---

[下载地址](https://typora.io/)

![](https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/typroadownload.png)

选择对应的版本，下载安装。

安装后，打开 文件->偏好设置->图像

![](https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/typroa-img1.png)

选择上传图片，上传服务选择PicGo（app），路径选择一会安装PicGo的路径。

其他设置，大家可以根据自己的喜好设置。

---

### 坚果云

---

[下载地址](https://www.jianguoyun.com/s/downloads)

![](https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/坚果云下载.png)

选择对应的版本下载，安装（安装过程没有截图，大家按照提示安装就可以）。最后把typroa的md文件保存在坚果云的同步文件夹下就可以了。

![](https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/坚果云.png)

![](https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/坚果云同步.png)



---

### PicGo

---

[下载地址](https://molunerfinn.com/PicGo/)

picgo是Github开源项目，大家下载自己需要的版本，其他平台大家可以参考文档安装。windows选择exe文件。安装后启动，刚开始不会有界面，右下角图标单击或者右键可以打开界面。

![](https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/picgo—download.png)

![](https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/picgo1.png)

到这里不要忘了去typroa上找一下picgo的安装路径。

---

### Github图床

---

[github.com](https://github.com/)

新建一个仓库，用做图床。（一定要公开不要私密，要不别人看不到图片）

setting->developer setting->personal access tokens

点generate new token

note 随便填，下面不知道每个选项都是什么意思，跟我一样全选上。

最后generate token

记住生成的token秘钥，

![](https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/github_setting1.png)

![](https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/github_setting2.png)

![](https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/github_setting3.png)

![](https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/github_setting4.png)

---

打开picgo，选择Github图床。

![](https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/picgo-github.png)

仓库名：用户名/仓库名

分支名：master

token：刚才生成的token秘钥

存储路径：是仓库下新建一个文件夹来作为图床，后面要有/

自定义域名;https://raw.githubsercontent.com/用户名/仓库名/分支

点确定即可。Github图床设置完成，可以上传一个图片试试。

Github主要是免费的，速度什么的就不行了。

---

### 阿里云图床

---

[阿里云网址](https://cn.aliyun.com/)

选择对象存储OSS，或者直接搜索也可以。购买的话，40GB一年才9元，现在买还有折扣，一年7.2元。

![](https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/aliyun_oss1.png)

![](https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/aliyun_oss2.png)

下单后，在控制台找到OSS。进入BUcket列表，创建bucket。

![](https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/aliyun_oss3.png)

![](https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/aliyun_oss5.png)

![](https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/aliyun_oss6.png)

bucket的名称大家自己想一个。读写权限改为公共读。

确定。记住外网的两个域名。

![](https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/aliyun_oss7.png)

下面来生成key。点击概览，右侧有一个常用入口，下面有一个Access Key。

![](https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/aliyun_oss8.png)

进入后，点击   创建Accesskey   验证手机，会造成ID和key，最好是保存一下。

![](https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/aliyun_oss9.png)

---

打开picgo，进入阿里云oss设置。

![](https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/picgo-aliyun.png)

keyid和keysecrect是刚才生成的ID和key。

存储空间名是bucket的名

存储区域是全世外网访问节点 去掉aliyuncs.com 前面的一串。

存储路径什么的大家根据自己的喜好来。

---

### 问题：

typroa验证上传时，不成功

![](https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/typroa_upload.png)

原因：应该是typroa的端口与picgo的端口不对应。修改一下picgo的server端口就行。

![](https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/picgo-server.png)

测试一下，成功了。

![](https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/typroa-upload1.png)

---

到这里就完事了！

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
