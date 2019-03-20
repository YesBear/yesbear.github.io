---
layout: post
title: "解决OpenCV编译错误error C2054"
data: 2019-3-20
categories: OpenCV学习笔记
---

最近因为工作需要，在win7平台上利用vs2013编译opencv源码时出现了，如下图所示的错误

![err0](https://yesbear.github.io/images/blog/解决OpenCV编译错误error_C2054/err0.PNG)

在网上查阅各种博客之后，大概原因是**现在广泛使用的C语言（C89或ANSI C）不支持inline这个关键字**，追根溯源之后发现直到C99标准才支持内联函数，所以编译过程会出错。解决办法也比较简单，仅需要在出现错误的源码的开始部分添加下列代码:

> #if defined(WIN32) && !defined(_cplusplus)
>
> #define inline _inline
>
> #endif

添加完毕后，再次编译顺利通过。