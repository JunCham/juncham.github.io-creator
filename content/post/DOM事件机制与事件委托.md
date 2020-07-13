---
title: "DOM事件机制与事件委托"
date: 2020-07-13T22:34:28+08:00
draft: false
---
# DOM事件机制与事件委托
DOM事件是JS与html交互的一种方式，它的实现主要通过事件流来实现。

事件流指的是页面接受事件的顺序，其中分为冒泡和捕获两种。

以下面的代码为例。

```
<body>
<div class="level1 x">
  <div class="level2 x">
    <div class="level3 x">
      <div class="level4 x">
        <div class="level5 x">
          <div class="level6 x">
            <div class="level7 x">
              
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</div>
</body>
```

捕获的监听是从最开始的祖先一代代的往下监听的，也就是从1到7的一级一级的监听有没有被触发。

冒泡则相反，从元素本身往上一代代的追溯，就好像气泡一点点往上冒。

W3C对事件模型的判定中

```markdown
div.addEventListener('click',fn,bool)
```
如果bool不传或者为falsy，事件按冒泡进行监听。

如果bool为true，事件按捕获进行监听。


e.target  是用户操作的元素。

e.currentTarget  是程序员监听的元素，其中this属于currentTarget。

另外，捕获不可打断，而冒泡可以被打断。

e.stopPropagation()可以中断冒泡，浏览器不再往上走。

而有一些事件不可取消冒泡，具体可以在MDN中搜索scroll event（浏览英文版，翻译后不全）；其中Bubbles表示“是否冒泡”；Cancelable表示“是否可以取消冒泡”。

在自定义事件当中，添加bubbles：true可以定义fn是可以冒泡的，添加cancelable：true可以定义fn可被取消冒泡，反之亦然。


## 事件委托：
借用某些元素或者操作对另外的元素或者新产生的元素进行监听或操作。

监听祖先：通过监听元素各父辈及以上的动态判断对元素的操作。

另外的DOM事件级别、详细的DOM事件等可见墨夜的[DOM事件详解](https://juejin.im/post/5c4bd01fe51d45522b4f6e4e "DOM事件详解")