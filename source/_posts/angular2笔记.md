---
title: angular2学习笔记
date: 2017-07-27 09:55:46
categories: 前端框架
tags:
- Angular2.0
toc: true
author: yutong16
---
### angular2学习笔记

>> 1.Observable对象与Promise对象的区别
>> 2.angular2中，组件中调用服务提供的请求方法，默认是不会发出实际请求的，因为RxJS中的Observable实现的是冷模式，只有当该对象的方法被组件实例订阅--subscribe()后，才能发出请求。订阅后的Observable对象返回的是一个Subsciption实例
>> 3.路由跳转，代码跳转Router.navigateByUrl()和Router.navitate()的底层工作机制基本一致，都是通过Router.shceduleNavtgation()方法来实现跳转。
不同的地方在于两个方法指定跳转的目标配置项的方式。Router.navigateByUrl()方法通过一个URL字符串或URLTree实例来指定。
Router.navigate()方法与RouterLink类似，通过链接参数数组来指定（通过链接参数数组生成URLTree()实例）。
除了这两个方法外，还支持extras参数定义跳转的具体行为