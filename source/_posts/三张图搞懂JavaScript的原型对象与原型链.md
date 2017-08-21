title: 三张图搞懂JavaScript的原型对象与原型链
author: XSong
tags:
  - 原型
  - 原型链
  - JavaScript
categories:
  - JavaScript
date: 2017-07-12 18:00:00
---
转自：http://www.cnblogs.com/shuiyi/p/5305435.html

对于新人来说，JavaScript的原型是一个很让人头疼的事情，一来prototype容易与\__proto__混淆，二来它们之间的各种指向实在有些复杂，其实市面上已经有非常多的文章在尝试说清楚，有一张所谓很经典的图，上面画了各种线条，一会连接这个一会连接那个，说实话我自己看得就非常头晕，更谈不上完全理解了。所以我自己也想尝试一下，看看能不能把原型中的重要知识点拆分出来，用最简单的图表形式说清楚。

我们知道原型是一个对象，其他对象可以通过它实现属性继承。但是尼玛除了prototype，又有一个\__proto__是用来干嘛的？长那么像，让人怎么区分呢？它们都指向谁，那么混乱怎么记啊？原型链又是什么鬼？相信不少初学者甚至有一定经验的老鸟都不一定能完全说清楚，下面用三张简单的图，配合一些示例代码来理解一下。
<!-- more -->
1. prototype和\__proto__的区别
![此处输入图片的描述][1]

    var a = {};
    console.log(a.prototype);  //undefined
    console.log(a.\__proto__);  //Object {}
    
    var b = function(){}
    console.log(b.prototype);  //b {}
    console.log(b.\__proto__);  //function() {}

2. \__proto__属性指向谁
![此处输入图片的描述][2]

    /*1、字面量方式*/
    var a = {};
    console.log(a.\__proto__);  //Object {}
    
    console.log(a.\__proto__ === a.constructor.prototype); //true
    
    /*2、构造器方式*/
    var A = function(){};
    var a = new A();
    console.log(a.\__proto__); //A {}
    
    console.log(a.\__proto__ === a.constructor.prototype); //true
    
    /*3、Object.create()方式*/
    var a1 = {a:1}
    var a2 = Object.create(a1);
    console.log(a2.\__proto__); //Object {a: 1}
    
    console.log(a.\__proto__ === a.constructor.prototype); //false（此处即为图1中的例外情况）

3. 什么是原型链
![此处输入图片的描述][3]

    var A = function(){};
    var a = new A();
    console.log(a.\__proto__); //A {}（即构造器function A 的原型对象）
    console.log(a.\__proto__.\__proto__); //Object {}（即构造器function Object 的原型对象）
    console.log(a.\__proto__.\__proto__.\__proto__); //null

  [1]: http://ac-myg6wstv.clouddn.com/2e7817d676e605e54e62.png
  [2]: http://ac-myg6wstv.clouddn.com/414693e5821245adeb86.png
  [3]: http://ac-myg6wstv.clouddn.com/e8f4cc45af11650de1f8.png