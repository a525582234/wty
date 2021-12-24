---
title: 傻瓜式搭建科学上网梯子（VPN）
date: 2021-12-20T12:00:06+09:00
description: 科学上网傻瓜式教程
draft: false
hideToc: false
enableToc: true ##侧边栏目录
enableTocContent: false ##文章内部的目录
author: wty                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                
authorEmoji: 🤖
tags:
- 科学上网
- 工具
categories:
- 工具文 ##series:-Themes Guide
image: images/feature1/graph.png
---

## 前言

搭建梯子主要分为以下几个步骤：

1. 租借vps;
2. 安装ssh远程登陆客户端；
3. 通过脚本安装Shadowsocks;
4. 安装SSR客户端，科学上网;

## 租借vps

上图所展示的就是国外常用的vps服务商，以前用过vultr和hostinger，体验并不算特别好，端口经常被封，网速还不怎么快。我现在用的是国内腾讯云的香港服务器。vultr里面买一个最低配置的也是一个月5美刀，腾讯云的话一年三百多，算起来价格差不多。所以还是强烈推荐国内用户使用腾讯云的服务器把！！

## 安装ssh远程登陆客户端

百度搜索finalShell

傻瓜式下一步安装；
连接到自己的服务器
![image-20211220223335002](/images/vpn/image-20211220223335002.png)

成功登录，出现[root@xxxx ~]#后，全部复制以下代码粘贴回车（一键安装脚本）

## 通过脚本安装Shadowsockss

输入一下命令回车执行

```shell
wget –no-check-certificate  https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocks.sh
```

![202001061578248107812711](/images/vpn/202001061578248107812711.jpg)

然后添加文件权限

```shell
chmod +x shadowsocks.sh
```

接着执行脚本，设置ss的密码端口和加密方式。
![image-20211220223925641](/images/vpn/image-20211220223925641.png)

```shell
./shadowsocks.sh 2>&1 | tee shadowsocks.log
```

然后按照要求输入密码、端口、加密方式

按任意键开始…或按Ctrl+C取消

输入完后，脚本执行自动安装，此时需要等待5-15几分钟安装完成。

![](/images/vpn/202001061578248189271712.png)

当出现上图信息时，说明SS已经搭建成功。

如果需要修改配置信息输入以下命令

```shell
vim  /etc/shadowsocks.json
```

这个就是配置文件，按a进行输入，:wq 进行保存；

![image-20211220224412248](/images/vpn/image-20211220224412248.png)

保存成功后执行一下命令进行重启

常用：

启动

```shell
ssserver -c /etc/shadowsocks.json -d start
```

停止

```shell
ssserver -c /etc/shadowsocks.json -d stop
```

重启

```shell
ssserver -c /etc/shadowsocks.json -d reload
```



## 安装SSR客户端，科学上网

客户端下载好直接双击就可以使用了，不需要安装；

Windows 版本SSR客户端

https://www.magento2u.com/wp-content/uploads/ShadowsocksR-4.7.0-win.zip

macOS 版本SSR客户端

https://www.magento2u.com/wp-content/uploads/shadowsocksr-android-3.5.4.zip

Android 版本SSR客户端

https://www.magento2u.com/wp-content/uploads/ShadowsocksX-NG-R8.zip

打开以后，在桌面右下角任务栏出现，点右键，点从粘贴板导入，然后就是见证奇迹的时刻，我们成功了。安卓端的ssr工具也很多，自行下载安装包安装就好，用法都差不多，ios下，国内市场的ssr客户端都下架了，需要去美区App Store下载，美区账号在淘宝买就好，一般一两块钱一个，ios端推荐Shadowrocket，不过要花钱买，几块钱，用我们之前注册的PayPal就好，也有个免费的Patatso Lite。用法都差不多，从剪贴板导入ssr地址就好。

![image-20211220225312622](/images/vpn/image-20211220225312622.png)

## 结语

相对于ssr我还是比较倾向于用ss来作为服务端，以前用ssr的时候经常段都被封，后面换了ss端口很少被封了。客户端使用ssr是因为体验感比ss强多了。。



## 

