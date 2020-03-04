---
title: "nanopi压力测试和散热能力"
catalog: true
date: 2020-03-04 20:11:50
subtitle: 
header-img: "https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/Demo.png"
tags:
- nanopi
- H5 cpu
- 压力测试
---
上手nanopi后，一直好奇它的H5cpu性能怎么样和铝壳散热能力怎么样，下面我们来大概看一下。做一下压力测试。

---

### 安装两个软件

---

==stress==：对CPU施压

```bash
$ sudo apt-get install stress
```



==htop==:CPU监控

```bash
$ sudo apt-get install htop
```

最好是更新一下系统。

---

### 开始测试

---

先连接一个ssh

```bash
$ sudo stress -c 4 -t 10000 -m 2 -d 2   
//4代表核数，10000代表时间,2代表内存进程，2代表硬盘进程
stress: info: [11352] dispatching hogs: 4 cpu, 0 io, 2 vm, 2 hdd
```



内存和硬盘设置为2 个，如果设置为4 的话就会影响nanopi的ssh进程。

查看CPU情况，新打开一个SSH，

```bash
$ htop
```

![](https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/nanopi_cpu1.png)

这是没有压力测试时候的情况，正常温度23左右，下面我们来进行压力测试。

![](https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/nanopi_cpu2.png)

一段时间后，温度稳定在60度，4个CPU均跑满了，内存用了一半。铝壳的散热现在还是压的住的。功率增加了一倍多。

```bash
$ sudo stress -c 4 -t 10000 -m 3 -d 2 
```

此时oled程序基本卡住，cpu跑满，内存700M左右，温度的话，铝壳散热是盖住了，大约70度，具体的就不知道了，oled显示已经乱了。

![](https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/cpu3.png)

开始真正的烧机。

```bash
$ sudo stress -c 4 -t 10000 -m 4 -d 4 
```

ssh已经开始连接不稳定，oled彻底罢工。温度还可以，

![](https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/cpu4.png)

作死跑了一个5cpu进程，还在运行，但其他进程已经不能正常工作了。

总体来说，这个nanopi还可以，铝壳散热完全盖的住。4核的H5也是完全ok。

---

【参考】[https://blog.csdn.net/qq_42869041/article/details/83834584](https://blog.csdn.net/qq_42869041/article/details/83834584)



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

