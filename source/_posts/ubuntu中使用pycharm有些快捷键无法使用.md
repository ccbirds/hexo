---
title: ubuntu中使用pycharm有些快捷键无法使用
catalog: true
date: 2020-02-27 08:57:49
subtitle:
header-img: "Demo.png"
tags: 
- ubuntu
- python
- pcharm

---

问题描述：在使用pycharm过程中，ctrl+c,ctrl+v,ctrl+d等快捷键无法使用。

解决办法：file->setting->Editor下面有一个Vim Emulation选项。

![VIm Emulation](1.png)
将Handler一列中的vim全部改为IDE，点Apply。

![VIm Emulation](2.png)
这样，快捷键就可以正常使用啦。

###### 链接：   
  [CSDN](https://blog.csdn.net/weixin_43662543/article/details/104069020)                        
  [简书](https://www.jianshu.com/p/f8779d6bd387)



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
