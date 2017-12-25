---
title: websocket说明
author: yutong16
date: 2017-12-01 14:20:59
categories: 技术博客
tags: 传输协议
---
### websocket使用说明
　　在一般的网络请求中，如HTTP协议，只能有前端发出请求后，后端根据协议的握手验证后，才能返回数据到前端。这样的数据传输方式，在有大量的HTTP请求时，会导致阻塞，例如在HTTP 1.1协议中，chrome就只能同时并发8条请求 。**这个问题在HTTP 2.0中已解决**
　　websocket是HTML5中一个可以在TCP连接上进行全双工通讯的协议。在WebSocket API中，只需要进行一个握手的操作后，浏览器和服务器之间就生成了一个专属的快速通道，两者之间可以互传数据。  
　　WebSocket对象通过`send()`方法来向服务器发送数据，并通过`onmessage`事件来接受服务器返回的数据。  
　　一般通过下面`new WebSocket()`的方式创建WebSocket对象：
> `var Socket = new WebSocket( url, [protocol] );`  

　　其中可以传两个参数，`url`是必传的参数，代表服务器的指定地址，`protocol`是可选参数，表示可接受的协议名。  

　　WebSocket对象拥有的属性如下：
1. Socket.readyState : 拥有4中连接状态，0-表示连接尚未建立；1-表示连接已建立，可以进行通信；2-表示连接正在关闭；3-表示连接已经关闭或者连接不能打开。
2. Socket.bufferedAmount : 只读属性bufferedAmount已被send()放入正在队列中等待传输，但是还没有发出UTF-8文本字节数。  

　　WebSocket对象的事件如下：
1. open: 事件处理程序-Socket.onopen,在连接时触发；
2. message: 事件处理程序-Socket.onmessage,客户端接受服务器数据时触发；
3. error: 事件处理程序-Socket.onerror,通信发生错误时触发
4. close: 事件处理程序-Socket.onclose,连接关闭时触发  

　　WebSocket方法如下：
1. WebSocket.send():使用连接发送数据；
2. WebSocket.close():关闭连接；  

为了建立一个WebSocket连接，客户端浏览器首先要向服务器发起一个HTTP请求，这个请求和通常的HTTP请求不同，包含了一些附加头信息，其中附加头信息`Upgrade:WebSocket`表明这是一个申请协议升级的HTTP请求，服务器端解析这些附加的头信息然后产生应答信息返回给客户端，客户端和服务器之间的WebSocket连接就建立起来了，双方可以互相传数据，并且这个连接持续到知道客户端或服务器的某一方主动关闭连接。