---
layout: post
title: 使用 AWS 部署 Node.js 项目
description: ""
modified: 2018-02-11
tags: [post frontend]
comments: true
share: true
---

### 前提
这是一篇最近尝试使用 AWS 的 12 个月免费额度以内的 EC2 部署 Node.js 项目的实践。第一次接触服务器和线上环境部署，遇到了不少问题，很多地方都是一通 Google 之后胡乱操作出结果的。方法估计也不是最好用的，写文章主要是给自己一个总结和分享，建议可以看文末那几篇写得比我清楚很多的文章。部署 Node.js 项目还有很多其他更好的方案，比如 Digital Ocean 的 $5 一月的 VPS，新浪云的更简单的部署也可以参考之前写的[文章](http://oxxd.github.io/nodejs-sinacloud)。还有 Heroku 好像也是一个不错的解决方案，以后尝试之后再总结吧。  
AWS 的 [12 月免费套餐](https://aws.amazon.com/cn/free/)提供相当多的服务，包括最主要用到的 EC2(服务器), RDS(关系型数据库), 是一个用来搭建小型网站的很好的解决方案。详细可以参考[这里](https://aws.amazon.com/cn/free/faqs/?ft=nf&refid=ha_a131L000005CqVRQA0)  
本来我以为 [Elastic Beanstalk](https://aws.amazon.com/cn/getting-started/tutorials/launch-an-app/) 也是包含在免费套餐里的，但是写这篇文章的时候发现并不是 XD。不然使用 Elastic Beanstalk 一键部署项目应该是更简单的选择。我也尝试过使用 Elastic Beanstalk 部署，但是代码上传完毕之后报错找不到 package.json 就不了了之了。  
另外说一下 AWS 的收费机制是账单制度，也就是每个月底会根据你的使用量来进行收费，所以要注意自己的服务用量，以避免额外收费。有可能产生额外收费的地方我稍后会总结在文末。

### 申请 AWS 账号
首先申请 AWS 账号需要提供信用卡，不确定是否需要双币信用卡。信用卡是为了验证用户信息以及后续产生的费用收费的。确认没问题之后可以在这里跟着向导进行[注册](https://aws.amazon.com/cn/free/)，期间会收到英文电话提示输入验证码，信用卡验证会扣一笔 1 美元的扣款，理论上是为了验证卡片，后续会退回。  
然后注意一下自己的注册区域，AWS 中国应该是最近两年才登陆国内的。我的账号似乎因为之前在美区注册过，注册了之后不能选择在国内区域建立主机。

### 创建 EC2 实例
<figure class="half">
    <a href="../images/nodejs-aws-tk.png">
        <img src="../images/nodejs-aws-tk.png" alt="">
    </a>
    <a href="../images/nodejs-aws-ec2.png">
        <img src="../images/nodejs-aws-ec2.png" alt="">
    </a>
	<figcaption><span>创建 EC2 实例</span>.</figcaption>
</figure>
登入控制台，准备创建 EC2 实例之前先确认一下所在区域。我这里选择的是 Tokyo 的，因为之前在美国的一个主机 SSH 登录不上去，不确定是什么原因。如果是国内账号应该能选择北京或者宁夏区域。

<figure class="third">
	<a href="../images/nodejs-aws01.png"><img src="../images/nodejs-aws01.png" alt=""></a>
	<a href="../images/nodejs-aws02.png"><img src="../images/nodejs-aws02.png" alt=""></a>
	<a href="../images/nodejs-aws03.png"><img src="../images/nodejs-aws03.png" alt=""></a>
	<a href="../images/nodejs-aws04.png"><img src="../images/nodejs-aws04.png" alt=""></a>
	<a href="../images/nodejs-aws05.png"><img src="../images/nodejs-aws05.png" alt=""></a>
	<a href="../images/nodejs-aws06.png"><img src="../images/nodejs-aws06.png" alt=""></a>
	<figcaption>创建 EC2 实例步骤</figcaption>
</figure>
创建 EC2 实例步骤  跟着向导一步步向下就可以了，这里我选择的服务器是 Ubuntu 的，Ubuntu 系统默认用户名是 ubuntu 一会儿会用到。

### 为 EC2 配置入站端口

### 连接 EC2 实例

### 安装 Node.js

### 安装 Apache + PHP + MySQL

### 部署

### 绑定 Elastic IP 以及自定义域名

### 填坑


### 参考文档
* [在Amazon EC2 上部署node.js应用](http://ned11.iteye.com/blog/1775898)
* [筆記｜在AWS EC2部署Node.js web教學](http://dez.logdown.com/posts/2017/04/07/aws-ec2-deploy-nodejs-web-app)
* [小白如何利用wordpress和aws从零搭建自己的个人网站](http://www.yours1989.com/52/)
* [在 Amazon AWS 搭建及部署网站：（一）申请、设置 AWS 服务](http://www.cnblogs.com/deltacat/p/amazon-aws-web-1.html)
* [Installing Node.js via package manager](https://nodejs.org/en/download/package-manager/#debian-and-ubuntu-based-linux-distributions)
* [To install the default LAMP stack in Ubuntu 10.04 and above](https://help.ubuntu.com/community/ApacheMySQLPHP)
* [How To Install Linux, Apache, MySQL, PHP (LAMP) stack on Ubuntu 16.04](https://www.digitalocean.com/community/tutorials/how-to-install-linux-apache-mysql-php-lamp-stack-on-ubuntu-16-04)
* [How To Install and Secure phpMyAdmin on Ubuntu 12.04](https://www.digitalocean.com/community/tutorials/how-to-install-and-secure-phpmyadmin-on-ubuntu-12-04)
* [AWS 免费套餐](https://aws.amazon.com/cn/free/)
* [AWS 10 分钟教程](https://aws.amazon.com/cn/getting-started/tutorials/)
* [通过 Amazon EC2启动 Linux 虚拟机](https://aws.amazon.com/cn/getting-started/tutorials/launch-a-virtual-machine/)
* [通过 AWS Elastic Beanstalk启动应用程序](https://aws.amazon.com/cn/getting-started/tutorials/launch-an-app/)