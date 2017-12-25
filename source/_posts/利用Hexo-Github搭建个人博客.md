---
title: 利用Hexo+Github搭建个人博客
author: yutong16
date: 2017-11-20 10:02:48
categories: 技术博客
tags: Hexo
---
### 利用Hexo+Github搭建个人博客
　　在这个百家争鸣的开放时代下，每个人都在各自的领域发光发热，作为一个每天早起晚归的板砖工，有一个记录自己板砖历程的记事本 **技术博客** 也是进入高级包工头的必备条件。所以在这里进行一下回顾一下博客搭建的过程。  
　　本次搭建博客需要以下各类资源：[一个github账户](https://github.com)，还有~~~~~好心情!!!  
  
下面进行搭建过程：
> 1.安装本地环境 **[nodeJS](http://nodejs.cn/download/)**
    　　在官网下载nodeJS对应的安装包后，点击按装包**以管理员身份运行**无脑下一步即可，安装完成后使用`cmd`命令打开控制台，输入`node -v`查看是否正确安装node服务，输入`npm -v`，查看是否已正确安装npm包管理器。本人成功截图如下：![node截图](https://raw.githubusercontent.com/yutong16/MarkDown-Image/master/HexoBlog/node-env.png)本人安装版本较早，现版本号可能会有所不同，但是没有影响。若出现其他情况，请重新安装nodeJS,或查阅相关资料进行处理。
> 2.安装**Hexo** 和**Git** 
    　　运行`npm install hexo -g`,在全局模式下安装hexo模块（默认最新版本），安装成功后运行`hexo`，cli中回下hexo相关指令,如下![hexo指令](https://github.com/yutong16/MarkDown-Image/blob/master/HexoBlog/hexo-env.png?raw=true),更多hexo相关信息请访问[Hexo API](https://hexo.io/zh-cn/docs/commands.html)。我们运行`hexo init <your blog's name>`初始化一个Hexo框架的简易博客，这样一个简易博客就搭建完成了。接下来进入博客文件夹，运行`hexo s`，框架部署成功后，如下：![hexo s](https://raw.githubusercontent.com/yutong16/MarkDown-Image/master/HexoBlog/hexo-s.png),在本地浏览器中输入`http://localhost:4000`即可访问到本地部署的博客。![本地demo](https://github.com/yutong16/MarkDown-Image/blob/master/HexoBlog/hexo-demo-web.png?raw=true) 然后登录[Git官网](https://git-scm.com/)，下载Git安装包，进行安装。 
> 3.将**Hexo博客发布到github上**
    　　上面成功后，我们登录github，并创建一个仓库,仓库名必须未**your_name.github.io**格式。这个github page的固定写法。![github rep](https://github.com/yutong16/MarkDown-Image/blob/master/HexoBlog/hexo-create-github-rep.png?raw=true) 
    　　建立完成后，拷贝仓库的连接![github link](https://github.com/yutong16/MarkDown-Image/blob/master/HexoBlog/hexo-github-https.png?raw=true),打开本地博客文件目录，编辑博客配置文件`_config.yml`,![配置文件](https://github.com/yutong16/MarkDown-Image/blob/master/HexoBlog/hexo-blog-config.png?raw=true),将配置文件的`deploy`属性改为如下，***注意`:`后面有一个空格***![配置文件](https://github.com/yutong16/MarkDown-Image/blob/master/HexoBlog/hexo-deployer-edit.png?raw=true)。完成后，我们关联了github,但是还的需要hexo中相应的模块将代码发布到github上，所以接着运行`npm install hexo-deployer-git --save`，安装完成后。设置连接github的账户，邮箱。![个人信息](https://github.com/yutong16/MarkDown-Image/blob/master/HexoBlog/github-user.png?raw=true)。接下来运行`hexo d -g`，也可以先运行`hexo g`，再运行`hexo d`。该命令含义是先生成静态文件，再发布到github上。在发布过程中，github会验证ssh密码，如果已经设置改密码，则会自动跳过。[设置连接github SHH教程](http://blog.csdn.net/lsyz0021/article/details/52064829)  
    　　发布成功后,即可访问该web站。  
> 4.**修改Hexo主题**  
　　Hexo最大的优势莫过于拥有丰富的主题风格，以及强大的社区论坛。在主题这块，个人比较倾向于[Next主题](http://theme-next.iissnan.com/)风格，还有[其他很多好看的主题](https://hexo.io/themes/)。  
　　这里我们进行一下主题的修改设置：  
　　1. 确定主题，运行`npm install --save <主题名称>`;  
　　2. 修改博客配置文件`_config.yml`中的`theme`属性，设置为主题名称;  
　　3. 运行`hexo d -g`，查看线上页面;
> 5.**Hexo相关常用命令**  
　　1. 新建分类，`hexo new page '名称'`;  
　　2. 新建博客，`hexo new '名称'`;  
    更多命令请学习[hexo官方文档](https://hexo.io/zh-cn/docs/)!
