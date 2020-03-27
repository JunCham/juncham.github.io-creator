---
title: "JS对象基本用法"
date: 2020-03-27T09:14:18+08:00
draft: false
---
# JS 对象基本用法

七种数据类型：四基两空一对象（number string bool symbol；null undefined；object）。

五个falsy值：null，undefined，0，NaN，''

对象是无序的数据集合，没有固定顺序，是键值对的集合，例如'name':'666'，name是键，666是它的值，他们成对是一个对象。

## 声明对象的两种语法

let obj = {'name': '666', 'work':'BAT'} (非正式写法)

let obj = new Object({'name': '666', 'work':'BAT'})  (正式写法)

键名是字符串，可以使任意符号，包括表情。

每个key都是对象的属性名，每个value都是对象的属性值（上面所说的值）。

let p1='name'

let obj ={p1:'666'}  这里的属性名是p1；

let obj ={[p1]:'666'}  这里的属性名是变量p1；

两个p1其实是不一样的东西。

## 如何删除对象的属性

语法：

delete obj.name  或者  delete obj['name']

要区分没有属性名和属性名的值undefined

没有属性名：'name' in obj ===false

属性名的值undefined(有属性但是还没赋予值): obj.name === undefined


## 如何查看对象的属性

语法：

查看自身所有属性：Object.keys(obj)

查看自身所有属性+公有属性： console.dir（obj）

判断一个属性是否是自身所有属性：obj.hasOwnProperty('toString')

原型是一个代表着（存着）对象的公有属性的对象。正常情况下一个对象的原型的原型是null。

'name' in obj表示查看obj 里面的'name'的所有属性，而obj.hasOwnProperty('name') 是查看obj的name是不是自身所有的属性。


查看属性的两种方法：

obj['key']

obj.key

上面两者是等价的，推荐使用第一种，熟练之后再第二种，因为其实第二种的obj是字符串。
而obj[key]求的是变量key的值的属性。
也就是说：

let 'key'：'666'

obj[key] ===obj['666']


## 如何修改或增加对象的属性

语法：

### 直接赋值：

let obj = {name:'666'}

obj.name= '666'

obj['name']='666'

### 批量赋值：

Object.assign(obj,{name:'666',work:'BAT'})

修改一个对象的共有属性例如：obj.toString='666'，并不会影响其他对象的共有属性，而是单独给了obj一个toString一个‘666’，但是其实obj的共有属性还在。

如果非要改，那就是obj.__proto__.toString = '666' 或者 Object.prototype.toString='666'

但是通常不会这样做，因为会影响其他对象。

修改一个对象的原型语法：

obj.__proto__ =common

let obj = Object.create(common)

例如obj.__proto__ = null 就直接抹掉了obj的原型（所有共有属性一口气凉凉）。

