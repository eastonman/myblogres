---
title: 使用hexo创建个人博客
date: 2016-10-21 21:30:38
tags: tech
---


本站采用的就是hexo，主题是next，hexo具有速度快、体积小、完全静态化、可塑性强等优点，摆脱了wordpress等冗杂的安装和庞大的数据库，适合用于个人博客
<!--more-->

# 如何用hexo建立个人博客
## 下载和安装hexo
hexo需要node.js的支持，前往[node.js官网](https://nodejs.org/en/)或[node.js中文网](http://nodejs.cn)下载和安装。  
在官网上有安装指导和问题解答，选择LTS版本安装，因为作者本人曾因为装了最新版的导致hexo不兼容安装失败  
hexo官方网站在[hexo.io](https://hexo.io/)，去官网上按照指引安装
> npm install hexo-cli -g

> hexo init blog

> cd blog

> hexo s

如果在本地4000端口看到了hexo的界面说明安装成功了  

---  

## 新建文章

> hexo new 文章名字

如果文章名字中间有空格那就必须加引号

> hexo new "文章   名字"

hexo就会在source/_post/下创建一个"文章名字.md"  
然后就可以直接用记事本编辑，也可以用各类markdown编辑器编辑。注意hexo采用的是Github Favored Markdown，书写规范与标准Markdown有微小区别，可以查阅github上的说明

---

## 发布文章

### Github Pages和各类git发布

Github Pages是一个免费的静态博客托管平台，国内外也有很多其它的静态博客托管平台是采用git方式提交页面的，所以常用的就是git-deploy  

安装hexo插件

> npm install hexo-deployer-git --save

修改__站点配置文件__中的deploy字段(尽量使用ssh方式连接服务器，防止在windows命令行中http连接错误)

```
deploy:
  type: git
  repo:"git@github.com:manyang901manyang901.github.io"

```
当然要先在git bash中配置好ssh私钥，保证可以通过ssh连接到服务器

---

## 通用的发布方法

在hexo生成的blog文件夹，使用

> hexo generate

hexo就会在文件夹里生成一个新的文件夹public，这个文件夹里包含了所有需要的静态文件，直接复制这个文件夹的所有文件到服务器上就可以了

## tags与categories分类

hexo中可以使用tags标签或categories分类来对文章进行整理，两者其实区别不大，此处以tags为例介绍如何使用。  
首先在欲分类的post的md文件的font里面找到（没有的新增）tags键，添加想要的键值，注意遵循YAML标准（也可以用JSON编写），注意冒号后面有一个空格，如

```

---
title: 使用hexo创建个人博客
date: 2016-10-21 21:30:38
tags: tech
---

```

然后输入命令

> hexo new page tags

hexo会在source文件夹下生成tags文件夹，新建index.md，修改这个md文件的font，如下

```
---
title: tags
date: 2016-11-11 20:23:38
type: "tags"
comments: false
---

```
然后照常更新和布署就可以看到有一个tags（标签）页面出现，并且自动生成好各个tag的文章
