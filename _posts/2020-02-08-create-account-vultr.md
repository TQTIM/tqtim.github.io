---
layout: post
title:  "Vultr注册、购买和V2ray搭建"
date:   2020-02-08 12:10:20
categories: vultr
author: tqtim
image: /img/2020-02-08/in.png
excerpt: vps选择与搭建
analytics: true
---

## 前言
搭梯子首要的是什么？当然是一台国外服务器！那么多服务器提供商，该选哪个呢？可以看[国外vps推荐]列举各大商优缺点，排行什么的仅做参考，挑选自己合适的。
不知道你之前有没有过vpn被封的经历，或者用手机端免费VPN时网速忒慢，尤其记得国庆阅兵的那段时间许多IP被封。所以我想说什么问题呢，
如果你买类似Bandwagon搬瓦工这种的话，一买就是一年的话，万一你幸运，搭好梯子，刚访问了个Google首页就被逮住了，那你钱岂不是白花了，因为bandwagon是绑定ip的。
现在说一下为什么要选vultr，vultr是按小时计费而且极其便宜，而且支持支付宝、微信付款，最便宜的2.5刀一个月（不合适，2.5$只提供ipv6），我们至少要选择3.5刀一个月的。
那按小时计费什么意思呢，刚刚上面提到过封ip的问题，按小时计费的话，封了我们就删掉这台服务器，重新开一台就好喽，重开就换新ip了。不过这几年vultr被国人玩坏了，
很多IP又被封了，你安装的服务器IP有很大概率选到已经被封了的，可以通过windos命名行ping IP来测试是否可用，或者[多地点Ping服务器]，如果IP不通可以再多开几台服务器，挑到可用的IP然后删除没用的服务器。

>Vultr采用时长计费方式，没有包年包月套餐。只要账户余额足够，服务器可以一直用。不需要时可销毁服务器，销毁后不再计费。

[国外vps推荐]:https://www.10besty.com/best-vps-hosting-services/
[多地点Ping服务器]:http://ping.chinaz.com/
## 注册
点击[注册Vultr账号](注: 限时注册Vultr送100刀，一个月有效，先消耗送的金额)

[注册Vultr账号]:https://www.vultr.com/
在中间注册页面输入你的电子邮箱地址（用来接收验证邮件以及通知），并设置账号密码。账户密码要求同时包含数字、小写字母，大写字母，并且不低于10个字符，填完点Create account

![in](/img/2020-02-08/in.png)

## 购买

进去后点左边Billing进入充值页面,选支付宝或微信充值金额
![money](/img/2020-02-08/money.jpg)

然后点击右边蓝色的“➕”（买新服务器）按钮，进入服务器购买页面。

![server](/img/2020-02-08/server.png)

首先是选择服务器类型，使用默认的“cloud compute”：

![server](/img/2020-02-08/1.png)

Server Location 项，选服务器的地理位置。移动用户建议选择日本或者新加坡节点；联通用户建议选择新加坡、杉矶机、硅谷和西雅图机房；电信用户建议选择洛杉矶、硅谷和西雅图机房。
因为vultr支持随时切换机房和更换ip，如果你选择的机房速度不满意，可以删除服务器重建。我选的是纽约的3.5$，日本新加坡好像最低5$。

![server](/img/2020-02-08/2.png)

Server Type，就是选择操作系统，选择ubuntu 18或centos 7 x64，因为网上很多科学配置上网教程和一键脚本都是运行在这个系统上。

![server](/img/2020-02-08/3.png)

可以选勾Enable IPv6，点右下角的“deploy now”按钮创建服务器

![server](/img/2020-02-08/4.png)

给服务器起个英文名

![server](/img/2020-02-08/5.png)

没问题的话点右下角的“deploy now”按钮创建服务器，等服务器正在install完成变为running

![server](/img/2020-02-08/6.png)

进入服务器可查看服务器信息

![server](/img/2020-02-08/7.png)

## 梯子V2ray的搭建

#### 连接服务器

- windows请下载软件xshell
- Mac可以下载ShellCraft

以windows的xshell为例：
![server](/img/2020-02-08/xshell.png)

确定后填服务器用户和名称（购买服务器信息里有），连接成功后就可以远程访问你的服务器了，然后在这可以部署科学上网脚本。

>注意：如果连不上，可能是这个ip被封了，毕竟用vultr干坏事的太多了，没关系，你可以同时开多台（千万不要着急删掉不能用的，不然还会分到之前不能用的ip），
一直开到找到能用的ip为止，然后就可以把其他的服务器删掉了

#### 运行一键脚本

如果你选的是ubuntu,可以参考[如何搭建v2ray，放弃使用ss和ssr]这篇教程。

如果你选的是centos，可以参考[V2Ray一键脚本]或者[V2Ray带伪装一键脚本]教程。

[如何搭建v2ray，放弃使用ss和ssr]:https://viencoding.com/article/207
[V2Ray一键脚本]:https://www.hijk.pw/centos-one-click-install-v2ray/
[V2Ray带伪装一键脚本]:https://www.hijk.pw/v2ray-one-click-script-with-mask/

#### 客户端下载

- [v2ray安卓客户端下载]
- [v2ray windows客户端下载]
- [V2Ray mac客户端下载]
- ios客户端自行百度Shadowrocket（俗称小火箭，注意不是shadowrocket VPN），借用别人境外apple id下载别人买好的Shadowrocket

[v2ray安卓客户端下载]:https://www.hijk.pw/v2ray-android-client-download/
[v2ray windows客户端下载]:https://www.hijk.pw/v2ray-windows-client-download/
[V2Ray mac客户端下载]:https://www.hijk.pw/v2ray-mac-client-download/

下载完客户端配置时：
- 类型：选Vmess
- 服务器、端口、用户名：填xshell远程一键脚本安装V2ray成功后的信息
- 算法：选aes-128-gcm

#### 问题

谷歌、火狐浏览器无法科学上网但其他浏览器可以，参见[谷歌浏览器插件SwitchyOmega]。

[谷歌浏览器插件SwitchyOmega]:https://www.qcgzxw.cn/2988.html

