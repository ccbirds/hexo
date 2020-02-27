---
title: nanopi neo2 black 上电使用
catalog: true
date: 2020-02-27 20:39:55
subtitle:
header-img: "Demo.png"
tags:
- nanopi
- ubuntu
- SSH
---
最近上手一个小东西，nanopi neo2 black，非常精致，可以运行linux core ，可以运行Ubuntu 内核，感兴趣可以淘宝，或者[官网](http://nanopi.org/)看看。

---
![](1.png)
![](2.jpg)
我买这个板子的时候，赠送了16GB的TF卡，里面有系统，所以我没有编译系统，关于系统的制作可以参考官方[文档](http://wiki.friendlyarm.com/wiki/index.php/NanoPi_NEO2_Black#Configure_System_with_npi-config)

---
### 1. 通过ssh连接

---
登录方式有有三种：串口、HDMI、ssh
串口需要使用debug UART引脚，然而板子出厂时这个引脚是不焊的，所以暂时没有办法使用串口登录。
HDMI是使用提供的模块，也是通过串口debug UART连接，所以暂时也无法使用。
只能使用SSH登录。
由于身边没有路由器，无法使用有线网络。只能使用无线网卡连接网络。
插上网卡，接上键盘，没有显示输出，只能盲打（大家如果能使用有线，nanopi会直接获取ip，就可以跳过这步了）
```bash
$ su root
fa
$ nmcli r wifi on //打开wifi
$ nmcli dev //显示网络设备，无线网卡是wlan0
$ nmcli dev wifi //扫描wifi信号
$ nmcli dev wifi connect "SSID" password "PASSWORD" ifname wlan0 //连接无线网，SSID是无线网名称，PASSWORD是密码
```
等一会就会从oled上看到IP了，使用xshell能过ssh就可以登录了，登录名pi，密码pi。root的密码fa。
![](3.png)
这样就连接成功了。

---
### 2. 更新

---
更改更新源为国内源
```bash
$ sudo vim /etc/apt/source.list
//加入以下源
deb http://mirrors.ustc.edu.cn/ubuntu-ports/ xenial main multiverse restricted universe
deb http://mirrors.ustc.edu.cn/ubuntu-ports/ xenial-backports main multiverse restricted universe
deb http://mirrors.ustc.edu.cn/ubuntu-ports/ xenial-proposed main multiverse restricted universe
deb http://mirrors.ustc.edu.cn/ubuntu-ports/ xenial-security main multiverse restricted universe
deb http://mirrors.ustc.edu.cn/ubuntu-ports/ xenial-updates main multiverse restricted universe
deb-src http://mirrors.ustc.edu.cn/ubuntu-ports/ xenial main multiverse restricted universe
deb-src http://mirrors.ustc.edu.cn/ubuntu-ports/ xenial-backports main multiverse restricted universe
deb-src http://mirrors.ustc.edu.cn/ubuntu-ports/ xenial-proposed main multiverse restricted universe
deb-src http://mirrors.ustc.edu.cn/ubuntu-ports/ xenial-security main multiverse restricted universe
deb-src http://mirrors.ustc.edu.cn/ubuntu-ports/ xenial-updates main multiverse restricted universe
```
有点慢，大家耐心等待（也可以是我的网慢）
执行更新命令
```bash
$ sudo apt-get update
$ sudo apt-get upgrade
```
![](4.png)

---
### 3.测网速
---
```bash
$ sudo apt install speedtest-cli //安装
$ sudo speedtest-cli //测试，有时可能测不出来
Retrieving speedtest.net configuration...
Retrieving speedtest.net server list...
Testing from China Mobile Guangdong (223.104.236.97)...
Selecting best server based on latency...
Hosted by ChinaMobile, Liaoning Branch,Dalian (Dalian) [247.24 km]: 75.654 ms
Testing download speed........................................
Download: 2.42 Mbit/s
Testing upload speed..................................................
Upload: 0.76 Mbit/s
我是热点连接，手机又被限速了所以很慢
```
我是热点连接，手机又被限速了所以很慢

---
大家可以为所欲为了，哈哈。


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

