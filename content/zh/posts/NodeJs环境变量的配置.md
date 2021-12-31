---
title: NodeJs环境变量的配置
date: 2021-12-30T16:32:06+09:00
description: NodeJs环境变量的配置
draft: false
hideToc: false
enableToc: true ##侧边栏目录
enableTocContent: false ##文章内部的目录
author: wty                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                
authorEmoji: 🤖
tags:
- VUE
- nodeJs
categories:
- 前端 ##series:-Themes Guide
image: /images/feature1/node.jpg
---

下载地址：https://nodejs.org/en/

1. 到nodejs目录下创建两个空文件夹，node_cahe和node_global![image-20211231111455919](/images/node环境变量/image-20211231111455919.png)

2. 然后通过命令添加配置

   ```
   npm config set prefix "E:/nodejs-16.3.1/node_global"
   npm config set cache "E:/nodejs-16.3.1/node_cache"
   ```

   ![image-20211231111836291](/images/node环境变量/image-20211231111836291.png)

3. 接下来配置系统环境变量，“我的电脑”-右键-“属性”-“高级系统设置”-“高级”-“环境变量”

   ![](/images/node环境变量/环境变量.png)

    进入环境变量对话框，在【系统变量】下新建【NODE_PATH】，输入【D:/Develop/nodejs/node_global/node_modules】，将【用户变量】下的【Path】修改为【D:/Develop/nodejs/node_global】

   ![image-20211231112402538](/images/node环境变量/环境变量1.png)

   ![](/images/node环境变量/环境变量2.jpg)

4. 测试

   ```
   npm version
   ```

   ![image-20211231114443974](/images/node环境变量/image-20211231114443974.png)

   