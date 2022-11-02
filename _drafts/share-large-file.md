---
layout: post
title: share large file
categories: ["linux"]
tags: ["tar","split","老司机技巧"]
---

> 介绍网上下资源（资源举例）的时候的分卷压缩
> 	不好之处
> 		慢
> 		去掉后缀有可能导致找不到其他分卷的提示
>
> 是否需要压缩？
> 	不需要，直接引用数据
> 		https://zhuanlan.zhihu.com/p/388273284
> 		https://blog.kaciras.com/article/4/WinRAR-vs-7zip-performance
> 	结论，我们要的不是压缩，只是打包以及大文件的分割功能
>
> 使用linux自带的打包功能tar和分割功能split就可以很好的满足需求
> 	tar功能介绍
> 	split功能介绍
> 	合并命令
> 		https://www.jianshu.com/p/a75b6efc875a
>
> 实例介绍1
> 	首先需要一个文件进行模拟，bb命令介绍
> 		https://blog.csdn.net/Mculover666/article/details/123848824
> 	单个大文件的分享
> 		https://www.jianshu.com/p/7e48978f51f1
>
> 实例介绍2
> 	打包与分割的合并命令
> 		解释命令
> 	linux下合并（cat）和解包（tar）的命令
> 	windows下合并（copy）和解包（tar）的命令
> 		制作成cmd文件一起分享，或者直接写好代码放分享页面
> 		https://blog.csdn.net/weixin_43729127/article/details/127032567
> 	

