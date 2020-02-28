---
title: nanopi neo2 black 音乐闹钟
catalog: true
date: 2020-02-28 10:37:00
subtitle:
header-img: "Demo.png"
tags:
- nanopi
- ubuntu
- 音乐闹钟
---
nanopi neo2 black 有音频接口，可以用它来放个音乐，折腾一下做个音乐闹钟吧。

---
### 首先查看cron是否运行
---
```bash
$ ps -ef | grep cron //查看cron是否运行
root       561     1  0 15:52 ?        00:00:00 /usr/sbin/cron -f
pi       18668 18655  0 21:07 pts/0    00:00:00 grep --color=auto cron
```
没有运行的话，启动一下
```bash
$ sudo service cron start //启动命令
$ sudo service cron stop  //停止命令
$ sudo service cron restart  //重启命令

```
---
### 设置定时播放音乐

---
安装sox用来播放mp3音乐
```bash
$ sudo apt-get install sox libsox-fmt-all
//libsox-fmt-all包含解码器
```
可以先播放一个音乐试试
```bash
$ play XXX.mp3
```
设置定时播放音乐
```bash
$ crontab -e //第一次使用会让你选择编辑器，选择vim就可以
//在文件末尾加
30 21 * * * aplay /home/pi/Music/XXX.mp3
//每天21:30播放音乐XXX.mp3
```
五个* * * * *
对应的分别是 分 时 天 月 周
重启一个cron服务就可以了
```bash
$ sudo service cron restart
$ service cron restart
```
---
大家每天定时听音乐吧！


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
