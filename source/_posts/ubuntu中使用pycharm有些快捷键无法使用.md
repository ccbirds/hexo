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
