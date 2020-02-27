---
layout: post
title: "给Github Page添加阅读量及字数统计"
data: 2019-6-10
categories: 前端
---

搭建这个Github Page已经很长时间了，一直很想知道文章的阅读量情况，像CSDN上的那个统计功能一样，之前尝试使用谷歌数据分析或是百度数据分析功能，效果没有想象中那么好，其次该服务不是永久免费，对于像我这样轻度博客使用者来说没性价比。直到在[ManateLazyCat](https://manateelazycat.github.io/index.html)的博客中发现一款叫做Hit Kounter的插件，可以用来进行统计。

针对使用Jekyll的GitHub Page，可以使用以下方法进行配置来，实现阅读量统计。

#### 0x00 添加Kit Kounter ####

找到GitHub Page工程文档中**include**文件夹里的**header.html**里<head>标签中下添加以下代码

>     <script src="https://cdn1.lncld.net/static/js/av-min-1.5.0.js"></script>
>     <script src="https://jerry-cdn.b0.upaiyun.com/hit-kounter/hit-kounter-lc-0.3.0.js"></script>

 #### 0x01 具体文章中引入 ####

在**_layouts**文件夹下**post.html**中加入以下代码

>  <div class="char-counter">
>           浏览<span data-hk-page="current"> - </span>次 字数{{page.content | strip_html | strip_newlines | remove: " " | size}} {{page.date | date: "%Y-%m-%d"}}
>         </div>

完成上述，即可实现以下效果

![图1](https://yesbear.github.io/images/blog/给Github_Page添加阅读量及字数统计/图1.PNG)

