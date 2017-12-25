---
title: DOM级别回顾
author: yutong16
date: 2017-11-22 10:34:51
categories: 技术博客
tags: JavaScript
---

### DOM一级  
　　DOM一级由两部分组成，一个是包含DOM Core模块，另一个是DOM HTML。其中DOM核心规定的是如何映射基于XML的文档结构，以便简化对文档中任意部分的访问和操作。DOM HTML模块则在DOM核心的基础上加以扩展，添加了针对HTML的对象和方法。
### DOM二级
　　DOM二级在DOM一级的基础上扩充了以下模块，实现了众多新类型和新接口：
+ DOM视图 `DOM Views`:定义了跟踪不同文档的接口;
+ DOM事件 `DOM Events`:定义了事件和事件处理的接口;
+ DOM样式 `DOM Style`:定义了基于CSS为元素应用样式的接口;
+ DOM遍历和范围 `DOM Traversal and Range`:定义了遍历和操作文档树的接口;  

### DOM三级
　　DOM三级进一步扩展了DOM，引入以统一方式加载和保存文档的方法——在DOM加载和保存 `DOM Load and Save`模块中定义；新增了验证文档的方法——在DOM验证 `DOM Validation`模块中定义。DOM三级也对DOM Core 进行了扩展，开始支持XML1.0规范，涉及XML Infoset,XPath和XML Base。  
***DOM 0级只是DOM历史上的一个参照点，实际上是不存在的，具体的来说的IE4.0和NN4.0早起的DHTML***。