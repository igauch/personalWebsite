---
title: JS执行
date: 2016-07-08 20:08:23
---

作为JS的系列文章，同样的提醒：我只是把对JS的认识用最粗鄙的语言进行讲解和记录，所以，阅读需谨慎！

1. JS在执行之前会先进行编译。这第一句话都可能被我带坏了，毕竟市面上都是说JS是动态的解释执行语言，但那又如何？！知道JS在执行之前是先进行‘编译’的就好。且看下面
    ```
    console.log(a);//undefined
    //把它复制到js文件里，并对下面一行打上断点，看控制台输出的是什么？undefined!说明在执行前进行了‘编译’
    //提醒：最好是在没有安装插件的浏览器环境执行，要不控制台可能会出现因插件带来的异常信息
    console.log(b);//Uncaught ReferenceError: b is not defined
    var a='a';
    ```
    对于上面的代码还要注意：
    JS存在变量提升的行为，即会把声明的变量提升到当前执行上下文的最顶端    
    所以`console.log(a)`输出的是`undefined`，注意！是undefined！不是a！变量提升提升的是变量的声明，而不是先执行`var a='a'`这句话。而`console.log(b)`却会抛出一个异常，虽然都是‘没定义’但一定要分清a是`undefined`,b是`not defined`是变量没有声明，是一个会阻塞JS执行的`ReferenceError`异常
    另外`ReferenceError`异常同作用域判断失败相关    
2. 堆栈    
不要问我什么是堆栈，我也不知道，不过我通常这么理解：堆，是存放数据的堆内存；栈就是用来执行的盒子容器(真的会被我带坏，哈哈哈)，这里讲栈，其实通俗来说，栈就是堆栈。    
    * 栈遵循先进后出，后进先出的特点，进出的是执行上下文，最先进入的全局上下文，并且在浏览器关闭时才被弹出
    * JS虽说是单线程的，但也能实现一些异步特性，进入堆栈的就有这么两种情况：同步情况和异步情况
        * 同步情况当然是当下进入
        * 异步情况常见的包括两种：延时和事件监听，事件监听常如AJAX，当他们的回掉函数执行时才创建其执行的上下文放入栈中：
        ```
        setTimeout(function () {
            console.log(1);
        });
        console.log(2);
        ```
        是不是先打印的2？虽然这里并没有设置时长，但依旧先执行`console.log(2)`，这便是堆栈的机制，JS执行的机制表现   