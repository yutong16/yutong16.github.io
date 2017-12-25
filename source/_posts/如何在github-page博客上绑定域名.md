---
title: 如何在github page博客上绑定域名
date: 2017-09-08 09:55:46
categories: 技术博客
tags:
- Hexo
toc: true
author: yutong16
---
### 如何在github page博客上绑定域名
> 由于国内访问github速度较慢，搭建在github.io上的博客也不例外。当我们通过国内域名解析后访问github.io，速度相对来说还是可以接受的。
> 1. 首先购买一个域名
> 2. 在域名解析菜单下，绑定两个解析方法
     a===>github.io  解析的ip地址
     CNAME===》yourname.github.io io地址
> 3. 在本地博客文件中source文件夹下面新建一个**CNAME**文件，没有后缀名。之后发布到github上。