---
title: hexo加上next主题及其他设置
date: 2016-04-27 14:58:28
tags: 
- hexo
- next
---
### 添加云标签  
next主题添加后,点击主页的标签按钮,会跳转到/tags目录,并报"Cannot GET /tags/"错误,这并不是我们想看到的。需要进行标签页面的创建。  

>hexo new page “tags”  

编辑刚新建的页面，将页面的类型设置为 tags ，主题将自动为这个页面显示标签云。页面内容如下：
>title: Tagcloud  
>date: 2014-12-22 12:39:04  
>type: "tags"  
>comments: false # 关闭这个页面的多说或者 Disqus 评论

在菜单中添加链接。编辑 主题配置文件 ，添加 tags 到 menu 中，如下:
>menu:  
>&nbsp;&nbsp;home: /   
>&nbsp;&nbsp;archives: /archives  
>&nbsp;&nbsp;tags: /tags

ok，进行如上操作后,执行hexo -g, hexo -s 命令就可以在本地看到预览了。
