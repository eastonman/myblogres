---
title: 使用shadowsocks实现科学上网
date: 2016-11-25 22:53:38
tags: notes
---


shadowsock是一个可以用一个端口实现sock4/sock5/socket代理的软件，其科学上网速度比同条件下VPN的速度要快，市面上许多科学上网服务商都提供shadowsock代理


<!--more-->

# shadowsocks
## 什么是shadowsocks
### 历史与版本

ss服务端一直只有Python版，而客户端支持跨平台，多语言，分为ss，ssr，shadowrocket，ss-libev等。  

早期shadowsocks由@clowindy在github上维护和开发，所有源代码均以GPLv3协议开源，2016年中，@clowindy被约谈，随即删除github上的代码仓库。  

后来@breakwa11重新在ss的基础上开发ssr，加入混淆头以防止GFW检测到服务器IP，但其效果遭到原版ss支持者的质疑，又经开始时@breakwa11曾违反GPLv3协议闭源，其开发历程一波三折，最终以其过硬的技术水平证明了ss确实存在漏洞。但本人使用南方电信暂未感到混淆与否的明显区别。

### shadowsocks原理
ss官方服务端使用的基于sockect代理原理，直接的包转发，




