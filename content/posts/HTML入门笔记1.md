---
title: "HTML入门笔记1"
date: 2020-02-02T21:18:51+08:00
draft: false
---

# HTML 入门笔记 1

终于开始做网页啦，虽然听课的时候比较好懂，但是一到要把每个标签之类的写出来感觉还是难的。主要分为 HTML 的起源、起手、章节标签、全局属性、内容标签。

## HTML 的起源

HTML 源自于李博士的天才捣弄，他依据网址搞出了 URL，根据网页搞出了 HTML，为了让两者更加完善，搞出了 HTTP。

## HTML 的起手

感叹号开局，emmet abbreviation 那个选项。

```markdown
<!DOCTYPE html>
<html lang="zh-CN">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <title>Document</title>
  </head>
  <body></body>
</html>
```

第一行表示文件类型是 html。
lang 代表语言，这里 zh-CN 表示简体中文。
UTF-8 兼容人类所有的语言，后面几行主要是防止网页的缩放，感觉以后会在博客写到的。

## 章节标签

h1~h6 表示各级大小的标题，同数字之间可以并列使用。
section 表示新的章节，里面可以使用下一级 hn。
p 表示一段话。
article 表示文章
main 主要内容
aside 旁支内容
div 划分段落

## 全局属性

全局属性是指所有的标签都可以有的属性。
主要包括：class、contenteditable、hidden、id、style、tabindex、title.
其中没事就别用 id,虽然它表示是唯一的，但是你不能确保它是唯一的，而却出现 bug 并不会报错。

## 内容标签

ol+il 有顺序的列表
ul+il 没有顺序的列表
dl+dd+dt dl 描述列表，dt 描述对象，dd 描述内容。
pre 所包含的内容如实呈现（多个空格，多个回车等）
a 用于添加网页链接
em 强调，重于语气，通常斜体表示，可以修改表现形式。
strong 强调，重于内容，通常加粗表示，同上。
code 用于表示计算机源代码等。

今天的内容就到这里啦。
