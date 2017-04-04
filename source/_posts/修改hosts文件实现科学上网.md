---
title: 修改hosts文件实现科学上网
date: 2016-12-11 23:04:03
tags: tech
---

世界上的ipv4地址有限，GFW无法做到过滤所有受限网站的ip，只能使用dns污染和劫持来阻止访问，这使得我们通过hosts来访问一些没有被封锁的ip

<!--more-->

# 修改hosts文件实现科学上网
## 什么是hosts文件
hosts文件就是系统存贮中用于指定特定域名的ip的文件

## hosts文件能干什么
既然GFW没办法封禁所有的谷歌ip，那么总是有一些ip在国内也能够访问，这时候用hosts重定向谷歌的域名到这些ip，再使用https避免dpi，就可以成功访问谷歌了


## 最新google hosts
hosts文件下载[hosts]( https://manyang901.github.io/2016/12/11/修改hosts文件实现科学上网/hosts)