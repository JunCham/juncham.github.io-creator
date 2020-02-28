---
title: "浅析URL"
date: 2020-02-28T10:49:32+08:00
draft: false
---
## 浅析URL

## URL
URL：统一资源定位符（Uniform Resource Locator），标准格式如下：

[协议类型]://[服务器地址]:[端口号]/[资源层级UNIX文件路径][文件名]?[查询]#[片段ID]

以https://zh.wikipedia.org:80/w/index.php?title=Special:随机页面为例, 其中：

1.https，是协议；

2.zh.wikipedia.org，是服务器；

3.80，是服务器上的网络端口号；

4./w/index.php，是路径；

5.?title=Special:随机页面，是询问。

![](/images/URL.png)

大多数网页浏览器不要求用户输入网页中“https://”的部分，因为绝大多数网页内容是超文本传输协议文件。同样，“80”是超文本传输协议文件的常用端口号，因此一般也不必写明。一般来说用户只要键入统一资源定位符的一部分


## DNS

DNS：域名系统（Domain Name System），它作为一个分布式数据库将域名和IP地址相互联系起来。IP用来定位一个设备，端口用来定位一个设备等的服务的。两者缺一不可。

nsloookup主要是用于查询DNS的信息，常用方法见：
https://www.jianshu.com/p/21dde6f7ce07

執行 nslookup 時可以直接在後面跟著我們要查詢的資料, 那麼 nslookup 會直接把結果傳回來。

如果只打入 nslookup [enter], 則進入交談模式, 出現提示符號 >, 此時 nslookup 會等待 user input command.

详细参考：http://faculty.ndhu.edu.tw/~comput/computer_c/training/hbc0122/dns-1.htm


## IP

ping加一个域名，可以得到该服务器的IP，IP主要是定位一个设备。域名就是IP，一个域名可以对应不同IP，负载均衡，防止过载。一个IP可以对应等多个不同的域名，共享主机，穷开发者会这样。域名通常有三种，com是顶级域名，qq.com是二级域名（俗称一级域名），www.qq.com（俗称二级），跟前者是父子关系。
