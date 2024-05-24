---
title: 部署 teedoc 生成的网站到 CDN
keywords: teedoc, 部署, CDN
desc: teedoc 生成的网站部署到 CDN
---




为了让各个地方的用户访问站点更加快速，可以使用 CDN 加速，
原理简单介绍就是先把网站放在一个源服务器上， 然后将这个资源同步到全国甚至全世界各地的节点上，
浏览器想要通过域名访问网站，这个域名指向的服务器只做一件事情，就是解析浏览器的地点，然后返回给给浏览器离浏览器最近的节点 IP 地址，然后浏览器直接访问最近的节点，从而实现了加速


先找一个 `CDN` 提供商，比如 阿里云 腾讯云 七牛云 都可以

然后步骤如下：

## 创建源服务器


自己创建源服务器，源服务器更新后，服务商自动同步更新到各个 CDN 节点

按照前面的方法建立一个网站 ，得到`域名A`， 比如`teedoc.github.io`


## 为网站添加 CDN 加速

如果是中国国内的服务商，需要先有一个备案的`域名B`，然后注册登录，添加一个 `CDN`服务， 设置回源站点为前面建立的网站`域名A`即可

然后访问`域名B`，服务商会自动从`域名A`出拉取网页同步到全国或者全球的各个节点，然后用户访问`域名B`就会重定向到离用户最近的节点的`IP`，以保证最快的浏览速度
