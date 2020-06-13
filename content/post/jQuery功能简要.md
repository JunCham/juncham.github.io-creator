---
title: "JQuery功能简要"
date: 2020-06-13T22:19:44+08:00
draft: false
---
# jQuery的功能简要

jQuery作为目前引用最广泛的库，也是寿命最长的库，有着很多优点，这里简要介绍一下它的一些功能。

## 1、jQuery 如何获取元素

通过元素的性质，例如id，class。例如:

```markdown
$("p")    //所有<p>元素
$(document)  //整个文档对象
$('#myId') //选择ID为myId的网页元素
```

或者以元素属性为基准，选择包含该属性或者是该属性值为“XX”的元素：

```markdown
$("[href='#']")
$('div.myClass')  //选择class为myClass的div元素
```

## 2、jQuery 的链式操作是怎样的

在选择网页元素进行操作后，return回到原来的api继续进行操作是jQuery方便优雅的一点。
通常需要在每个操作上加上return api或return this。如果需要考虑到返回当前api的前一个则需要加入相应的操作。

```markdown
$('test')        //对test操作
  .find(div3) //找到div3这个元素
  .add(blue) //对test加blue
  .end()        //退回到div3的前一个api
```

## 3、jQuery 如何创建元素

jQuery创建新元素只要把新元素传入jQuery的构造函数即可。

```markdown
append()   //在被选元素的结尾插入内容
prepend() //在被选元素的开头插入内容
after()       //在被选元素之后插入内容
before()    //在被选元素之前插入内容
```

## 4、jQuery 如何移动元素

```markdown
.insertAfter()和.after()         //在现存元素的外部，从后面插入元素
.insertBefore()和.before()   //在现存元素的外部，从前面插入元素
.appendTo()和.append()    //在现存元素的内部，从后面插入元素
.prependTo()和.prepend() //在现存元素的内部，从前面插入元素
```
$('test').inserttAfter('p')和$('p').after('test')

两者作用相同，都是将test移动到p后面，区别在于返回的都是前一个括号里面的元素。

## 5、jQuery 如何修改元素的属性

$(selector).attr(attribute,value)  // 取出或设置某个属性的值，attribute：对应各属性，vlaue对应的属性值。


具体的可以参考阮一峰的[jQuery设计思想](http://www.ruanyifeng.com/blog/2011/07/jquery_fundamentals.html "jQuery设计思想")

以及[jQuery API 中文文档](https://www.jquery123.com/ "jQuery API 中文文档")
