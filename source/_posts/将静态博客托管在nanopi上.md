---
title: "将静态博客托管在nanopi上"
catalog: true
date: 2020-03-01 20:11:50
subtitle: 
header-img: "https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/Demo.png"
tags:
- nanopi
- 博客托管
---

最近买了一个nanopi，里面运行的是Ubuntu，可以做很多事情，我便想到用来做我博客的服务器。这前我是把我的博客托管在Github上。Github在国内的速度还是比较慢的。而且以前有被墙过。

---

在nanopi上安装nginx

```bash
$ sudo apt install nginx
```

编辑nginx的设置文件

```bash
$ vim /etc/nginx/nginx.conf
```

在http里面加

```bash
server {
                listen          80 default_server;
                server_name     ccbirds.cn;//自己的域名
                root            /home/fa/hexo-blog; //clone下来的位置
                location / {
                }
        }

        server {
                listen          80;
                server_name     www.ccbirds.cn;
                return          301 http://ccbirds.cn$request_uri;
        }
```

开启nginx服务

```bash
$ sudo service nginx start  //启动命令
$ sudo service nginx stop   //停止命令
$ sudo service nginx restart  //重启命令
```

如果报错，根据提示查看报错原因，

```bash
$ sudo nginx -t  //查看配置文件是否有问题
$ ps -ef | grep nginx  //显示nginx的进程
$ sudo kill -quit 14952  //杀死进程
```

现在使用IP或者域名就可以访问了。

---

可是每次更新博客都要手动clone一下吗？

网上有使用webhooks自动部署的方法，不过本人比较笨，没有弄好，感兴趣的可以试试，成功了记得告诉我一声。

我采用了比较笨的一种方法，每天定时删除hexo-log，定时重新clone一次。

```bash
$ crontab -e 
//在最后加上两句
0 0 * * * sudo rm -rf /home/fa/hexo-blog  //每天零点删除hexo-blog
5 0 * * * sudo git clone https://github.com/ccbirds/ccbirds.github.io.git /home/fa/hexo-blog  //每天零点五分 重新clone
$ sudo service cron restart  //重启cron
$ service cron restart
```

五个* * * * *
对应的分别是 分 时 天 月 周

不是很完美，先这样吧。

---

遇到的问题：

启动nginx时，报错，80端口已经被占用，看了一下进程，发现是nginx自己占用了80端口。使用nginx -t 看一下问题，是/etc/nginx/sites-enabled/default这个也在使用80端口，把这里的80改成其他端口就没有问题了

---

欢迎大家访问！

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


