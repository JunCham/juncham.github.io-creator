---
title: "HTML常用标签"
date: 2020-02-04T22:29:44+08:00
draft: false
---

# HTML常用标签
## a标签
很常用，通常是跳转到内部页面或者外部页面，或者手机或邮箱。

<a href> href是hyer与reference的结合，超链接，可以在当前网页打开相应的链接。可以打开http、htttps、或者直接以//开头的网页，后者是默认最高级会逐级跳转。

添加tel+手机号码，如果是在打开可以直接呼唤号码。

添加mailto+邮箱，可以直接跳转到发邮件。

另外添加目录也可以跳转，html里面/默认是当前的文件是根目录。

javascript伪协议写法，<a href="javascript:代码;">按钮</a>。代码是对应想要的代码，如果想要点击之后毫无反应就什么都不写。

也可以跳转相应的id，id=xxx

<a target>决定链接在何处打开，其中

1 _blank 是在新的空白页面打开

2 _top 在上层页面打开

3 _parent 在当前连接所在的上层打开

4 _self 在当前链接打开

如果是target=xxx，则会创建新的窗口自动命名xxx并打开。

<a download> 下载对应的网页，有可能不支持

<a ref=noopenr> 防止某些bug，以后会说到


## img标签
作用是发出get请求，展示一张图片。

<img src=>等号后面接图片的地址，可以是网络上的地址也可以是目录里面的。
alt：替换的，或者可选择的。通常是图片加载失败就替换展示的图片（eg：404）。

width、height：宽度和高度，只写一个另一个就自动对应变化。如果不对应就可能图片变形。如果加载超过页面宽高就填写100%（响应式）。

onload、onerror：用于监听图片是否加载成功。写在img命令的下面，用script包含着。

对应名称.onload=funcion

console.log('图片加载成功')

xxx.src=yyy路径  进行补救


## table标签
主要用于制作表格。里面通常只包含thead、tbody、tfoot三个标签。但是彼此之间调换顺序并无影响。这三者里面包含tr（row，行）里面包含th（thead缩写、作表头），td（data，内容）。

如果需要首行和首列都是表头，可以在tbody里面第一个使用th，后面内容td，如此类推。


### table的相关样式
table-layout：auto就自动按内容决定行列距，fixed就各行列平均，由第一列或第一行的宽度决定。

border：10px，solid，red。就是表格间相距10像素，实线，红色。

table-spacing：表格之间的距离。

table-collapse：表格距离的合并，spacing=0时就是常见的Excel那样。
