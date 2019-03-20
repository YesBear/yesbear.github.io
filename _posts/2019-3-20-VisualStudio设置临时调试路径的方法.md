---
layout: post
title: "Visual Studio设置临时调试路径的方法"
data: 2018-3-20
categories: Visual Studio
---

在Visual Studio中进行调试程序时，需要进行连接外部动态链接库（即DLL），因是临时调试，且比较多，此时可以通过以下途径进行设置

> 工程属性=》调试=》环境，在“环境”一栏中输入path=**添加上dll的路径**