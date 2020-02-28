---
title: nanopi_neo2_black_防烧屏设置
catalog: true
date: 2020-02-28 15:07:46
subtitle:
header-img: "Demo.png"
tags:
- nanopi
- python
- oled
---
oled长时间点亮一个点，付出现烧屏现象，为了避免烧屏。我们将oled设置为闪屏。

---
关于oled模块驱动的安装，可以参考[官方文档](http://wiki.friendlyarm.com/wiki/index.php/NanoHat_OLED)
```bash
$ git clone https://github.com/friendlyarm/NanoHatOLED.git
$ cd NanoHatOLED
$ sudo -H ./install.sh
```

---
#### cd到oled源文件目录,修改两个文件
```bash
$ cd /root/NanoHatOLED/BakeBit/Software/Python
//使用python控制
$ sudo vim bakebit_nanohat_oled.py
//加入一条语句
while True:
    try:        
        oled.clear_raw() //加入这个语句，其他语句不变
        draw_page()
        lock.acquire()
        page_index = pageIndex
        lock.release()
   
$ sudo vim bakebit_128_64_oled.py
//加入下面的函数
def clear_raw():
    for j in range(8):
        setTextXY(0,j)    
        for i in range(16):  #clear all columns
            putChar(' ')  
```

#### 清除原进程，启动新进程
```bash
$ ps aux | grep python //查看进程
root     25913  3.8  1.4  22380 14648 pts/0    S    14:23   0:35 python bakebit_nanohat_oled.py
pi       26617  0.0  0.0   7284   544 pts/0    S+   14:39   0:00 grep --color=auto python
$ sudo pkill -f bakebit_nanohat_oled.py 
//结束进程
$ sudo python bakebit_nanohat_oled.py
// 重启进程 
$ sudo python bakebit_nanohat_oled.py &
// 重启进程 后台运行
```

---
这样就不会烧屏了！

<div id="gitalk-container"></div>
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/gitalk@1/dist/gitalk.css">
<script src="https://cdn.jsdelivr.net/npm/gitalk@1/dist/gitalk.min.js"></script>
<script src="/js/md5.min.js"></script>
<script >
var gitalk = new Gitalk({
  clientID: '30ef5ef3ee69767d3c66',
  clientSecret: '89eb8a0b3782e394a2ef7d8901770a7d5327dc23',
  repo: 'ccbirds.github.io',
  owner: 'ccbirds',
  admin: ['ccbirds'],
  id: md5(location.pathname),      // Ensure uniqueness and length less than 50
  distractionFreeMode: false  // Facebook-like distraction free mode
})
gitalk.render('gitalk-container')
</script>
