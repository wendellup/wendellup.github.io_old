---
title: DigitalOcean反向代理google失败
date: 2016-05-12 09:57:21
tags: 
- nginx
- vps
---

### 议题:vps可以访问谷歌,准备用nginx搭建反向代理,这样不用翻墙也可以通过vps访问谷歌 ###

#### 尝试一 ####

按照这篇文章(http://www.v2ex.com/t/126028) 中的方式进行了nginx配置,尝试http方式失败,直接申请了ssl证书开始尝试https方式反代谷歌,对应的nginx配置文件为(nginx.conf\_google见文章结尾)。  
配置好nginx后访问我的https域名(https://www.wendellup.com) ,google主页是可以显示的,但是只要一搜索就跳转到https://www.wendellup.com/ipv4/sorry/IndexRedirect?continue=https://www.google.com/search%3..... 
![](http://ww2.sinaimg.cn/large/ab1cb1a6gw1f3rkvca4unj20rb0d4wfn.jpg)
好郁闷,一直找不到原因。纠结了好长时间,不知是配置问题还是环境问题。于是乎尝试配置反代百度,对应的nginx配置文件为(nginx.conf\_baidu见文章结尾)重启后nginx后访问域名,主页展现后搜索都正常,这下可以确认不是配置问题了。
![](http://ww3.sinaimg.cn/large/ab1cb1a6gw1f3rkwf56o1j20sr0e340j.jpg)
![](http://ww2.sinaimg.cn/large/ab1cb1a6gw1f3rkvfwmisj20pw0evq75.jpg)
#### 尝试二 ####

确认不是配置问题后尝试了github上知名wen.lu的配置方法(https://github.com/cuber/ngx\_http\_google\_filter\_module/blob/master/README.zh-CN.md) ,按照他的安装配置方式进行搭建。搭建成功后访问我的https域名(https://www.wendellup.com) ,主页访问正常,但一搜索也出现问题。
![](http://ww4.sinaimg.cn/large/ab1cb1a6gw1f3rkvi15xfj20wr0g1gpz.jpg)
在网上进行了搜索(vps的ip被谷歌当成机器人),大概原因是因为有人用DO和我相邻的IP段对google做坏事,导致我的vps的ip无法正常反代google。这样也大致猜出尝试一中反代谷歌搜索失败的原因咯。

#### 总结 ####

一顿操作只能反代baidu成功,哈哈哈,纯当学习了吧。翻墙还是老老实实的用我的[greenVPN](http://gjsq.me/3799512)吧。



