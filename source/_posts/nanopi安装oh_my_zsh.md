---
title: "nanopi安装oh my zsh"
catalog: true
date: 2020-03-10 15:00:00
subtitle: 
header-img: "https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/Demo.png"
tags:
- nanopi
- oh my zsh
---

nanopi是基于ubuntu16.04LTS，自带的bash终端总觉的有点不舒服，有一款终端不错还可以更换主题。oh my zsh。[https://ohmyz.sh/](https://ohmyz.sh/) 

下面我们来反nanopi的终端美化一下。

---

首先安装zsh，我们先看一下，我们有没有zsh。

```bash
$ cat /etc/shells
/bin/sh
/bin/dash
/bin/bash
/bin/rbash
$ echo $SHELL  //查看我们当前使用的shell
/bin/bash
```

当前，我们是没有安装zsh的。使用的是默认的bash。

---

### 安装

---

先安装zsh

```bash
$ sudo apt-get install zsh
Reading package lists... Done
Building dependency tree 
Reading state information... Done
The following packages were automatically installed and are no longer required:
  aspell aspell-en dictionaries-common emacsen-common libaspell15 libenca0 libfaad2 libjack-jackd2-0 libmodplug1
  libmpcdec6 libopus0 libopusfile0 librcc0 librcd0 libresid-builder0c2a libsidplay2v5 libsidutils0 libspeex1
  libtag1v5 libtag1v5-vanilla libtagc0 libtext-iconv-perl
Use 'sudo apt autoremove' to remove them.
The following additional packages will be installed:
  zsh-common
Suggested packages:
  zsh-doc
The following NEW packages will be installed:
  zsh zsh-common
0 upgraded, 2 newly installed, 0 to remove and 250 not upgraded.
Need to get 3,724 kB of archives.
After this operation, 14.0 MB of additional disk space will be used.
Do you want to continue? [Y/n] y
Get:1 http://mirrors.ustc.edu.cn/ubuntu-ports xenial-security/main arm64 zsh-common all 5.1.1-1ubuntu2.3 [3,182 kB]
Get:2 http://mirrors.ustc.edu.cn/ubuntu-ports xenial-security/main arm64 zsh arm64 5.1.1-1ubuntu2.3 [542 kB]
Fetched 3,724 kB in 5s (648 kB/s)
debconf: delaying package configuration, since apt-utils is not installed
Selecting previously unselected package zsh-common.
(Reading database ... 45962 files and directories currently installed.)
Preparing to unpack .../zsh-common_5.1.1-1ubuntu2.3_all.deb ...
Unpacking zsh-common (5.1.1-1ubuntu2.3) ...
Selecting previously unselected package zsh.
Preparing to unpack .../zsh_5.1.1-1ubuntu2.3_arm64.deb ...
Unpacking zsh (5.1.1-1ubuntu2.3) ...
Setting up zsh-common (5.1.1-1ubuntu2.3) ...
Setting up zsh (5.1.1-1ubuntu2.3) ...
update-alternatives: using /bin/zsh5 to provide /bin/zsh (zsh) in auto mode
update-alternatives: using /bin/zsh5 to provide /bin/rzsh (rzsh) in auto mode
```

查看一下有没有安装上，

```bash
$ cat /etc/shells
/bin/sh
/bin/dash
/bin/bash
/bin/rbash
/bin/zsh
/usr/bin/zsh   //已经有zsh了
```

把zsh修改为默认shell

```bash
$ chsh -s /bin/zsh
```

安装oh my zsh

```bash
$ sh -c "$(wget https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh -O -)"

```

![](https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/nanopi_ohmyzsh.png)

这样就安装上了

---

### 修改主题

---

更改主题和加插件，编辑文件==~/.zshrc==

```bash
$ vim ~/.zshrc
ZSH_THEME="ys"   //更改主题，我比较喜欢ys
$ source ~/.zshrc
```

![](https://ccbirds-blog.oss-cn-beijing.aliyuncs.com/blog_img/ohmyzsh1.png)



可以在==~/.oh-my-zsh/themes==查看都有什么主题

---

### 安装插件

---

#### 安装autojump插件

```bash
$ sudo apt-get install autojump
$ vim ~/.zshrc
#在最后一行加入
. /usr/share/autojump/autojump.sh
$ source ~/.zshrc   生效
```

#### 安装自动补齐插件

```bash
$ cd ~/.oh-my-zsh/plugins/
$ mkdir incr
$ cd incr
$ wget http://mimosa-pudica.net/src/incr-0.2.zsh
$ vim ~/.zshrc
#在最后加入 
source ~/.oh-my-zsh/plugins/incr/incr-0.2.zsh
$ source ~/.zshrc 生效
```

#### 安装语法高亮zsh-syntax-highlighting

```bash
$ cd ~/.oh-my-zsh/plugins
$ vim ~/.zshrc
$ git clone https://github.com/zsh-users/zsh-syntax-highlighting.git
#在最后加入
source ${(q-)PWD}/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh
$ source ~./zshrc 
```

#### 安装语法历史记录

```bash
$ git clone git://github.com/zsh-users/zsh-autosuggestions $ZSH_CUSTOM/plugins/zsh-autosuggestions
$ vim ~/.zshrc
# 修改
plugins=(git extract z zsh-autosuggestions)
$ source ~/.xshrc
```

现在终端好看了许多

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


