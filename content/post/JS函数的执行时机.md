---
title: "JS函数的执行时机"
date: 2020-05-08T00:24:14+08:00
draft: falese
---
## 关于JS函数的调用时机

通常来说是按代码的执行顺序进行执行的。

```markdown
let i = 0
for(i = 0; i<6; i++){
  setTimeout(()=>{
    console.log(i)
  },0)
}
```

上面的代码会打出6个6，而不是1，2，3，4，5。这是因为setTimeout表示这个代码运行完毕之后尽快执行。前提是这个for语句执行完再去做，
也就是说，执行完了，这个唯一的i变成了6，退出了for循环之后执行，那就是6个6了。

```markdown
for (let i = 0; i<6; i++){
  setTimeout(()=>{
    console.log(i)
  },0)
}
```

上面的代码则会打印出 0、1、2、3、4、5 ，这是因为JS为了满足新手的幻想，在for循环里面每一次都新添加了一个i（i不唯一了），所以分别对应的打出了那个i。

这里的setTime意义不大了。

另外还有以下三种方式可以达到上面的效果。

1、闭包

```markdown
let i 
for(i = 0; i<6; i++){
  !function(j){
      setTimeout(()=>{
        console.log(j)
      },0)
  }(i)
}
```

2、利用 setTimeout 的第三个参数,将i传进去

```markdown
let i
for(i = 0; i<6; i++){
    setTimeout((value)=>{
      console.log(value)
    },0,i)
}
```

3、利用 const 关键字

```markdown
let i
for(i = 0; i<6; i++){
    const x = i
    setTimeout(()=>{
      console.log(x)
    })
}
```

const声明 创建了一个值的只读引用，固定了每一个新出现的i，但是因为引用的内容i是可变的，于是可以不断变换x的值.

## 关于this

```markdown
let person = {
name: 'frank',
sayHi(    ){
console.log(`你好，我叫 ` + this.name)
}
}
```

person.sayHi()

相当于

person.sayHi(person)

this代表了将要用到的未知称呼的变量，将其传给了代码里面的this，然后this又传给了要用到它的函数。

两种调用方法：

小白调用法：

person.sayHi()

person自动传到函数里面，作为this。

大师调用法：

person.sayHi。call(person),手动传入person。

this的两种使用方法：

隐式传递：

fn(1,2)  //相当于fn.call(unefined,1,2)，如果不添加undefined，就会被传给this，fn得到的就只有2。

obj.child.fn(1) //相当于obj.fn.call(obj.child,1)

显式传递：

fn.call(undefined,1,2)

fn.apply(undefined,[1,2])
