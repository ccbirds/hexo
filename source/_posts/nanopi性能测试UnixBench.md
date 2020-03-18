---
title: "nanopi性能测试unixbench"
catalog: true
date: 2020-03-12 20:11:50
subtitle: 
header-img: "https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/Demo.png"
tags:
- unixbench
- nanopi
---
入手nanopi不知道它的性能怎么样，下面我们来使用unixbench，对nanopi跑分测试一下

---

只需要简单的三个命令就可以

```zsh
$ wget --no-check-certificate https://github.com/teddysun/across/raw/master/unixbench.sh
$ chmod +x unixbench.sh
$ sudo ./unixbench.sh  //会自动检查依赖
```

![](https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/unixbench1.png)

时间有点长，稍等一会

![](https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/unixbench2.png)

```zsh
========================================================================
   BYTE UNIX Benchmarks (Version 5.1.3)

   System: NanoPi-NEO2-Black: GNU/Linux
   OS: GNU/Linux -- 4.14.111 -- #1 SMP Thu Dec 19 19:12:27 CST 2019
   Machine: aarch64 (aarch64)
   Language: en_US.utf8 (charmap="UTF-8", collate="UTF-8")
   10:22:26 up 18 min,  3 users,  load average: 0.68, 0.52, 0.32; runlevel 5

------------------------------------------------------------------------
Benchmark Run: Fri Mar 13 2020 10:22:26 - 10:50:55
0 CPUs in system; running 1 parallel copy of tests

Dhrystone 2 using register variables        6580436.9 lps   (10.0 s, 7 samples)
Double-Precision Whetstone                     1155.9 MWIPS (10.0 s, 7 samples)
Execl Throughput                               1316.7 lps   (29.9 s, 2 samples)
File Copy 1024 bufsize 2000 maxblocks        145034.8 KBps  (30.0 s, 2 samples)
File Copy 256 bufsize 500 maxblocks           45162.1 KBps  (30.0 s, 2 samples)
File Copy 4096 bufsize 8000 maxblocks        351000.7 KBps  (30.0 s, 2 samples)
Pipe Throughput                              440132.8 lps   (10.0 s, 7 samples)
Pipe-based Context Switching                  66182.3 lps   (10.0 s, 7 samples)
Process Creation                               2560.7 lps   (30.0 s, 2 samples)
Shell Scripts (1 concurrent)                   1991.9 lpm   (60.0 s, 2 samples)
Shell Scripts (8 concurrent)                    656.1 lpm   (60.1 s, 2 samples)
System Call Overhead                         785715.5 lps   (10.0 s, 7 samples)

System Benchmarks Index Values               BASELINE       RESULT    INDEX
Dhrystone 2 using register variables         116700.0    6580436.9    563.9
Double-Precision Whetstone                       55.0       1155.9    210.2
Execl Throughput                                 43.0       1316.7    306.2
File Copy 1024 bufsize 2000 maxblocks          3960.0     145034.8    366.2
File Copy 256 bufsize 500 maxblocks            1655.0      45162.1    272.9
File Copy 4096 bufsize 8000 maxblocks          5800.0     351000.7    605.2
Pipe Throughput                               12440.0     440132.8    353.8
Pipe-based Context Switching                   4000.0      66182.3    165.5
Process Creation                                126.0       2560.7    203.2
Shell Scripts (1 concurrent)                     42.4       1991.9    469.8
Shell Scripts (8 concurrent)                      6.0        656.1   1093.5
System Call Overhead                          15000.0     785715.5    523.8
                                                                   ========
System Benchmarks Index Score                                         372.0



======= Script description and score comparison completed! ======= 

```

这是结果，分不是很高。

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