---
layout: txl
title: Mac OS Development - 2 - Xcode Hello World
---

###Remember###
 - creating a metod: -(returnType) methodName:(arg)a;
 - calling a method: [objectName methodName:a];
 - Accessing objects using dot
 ex: Rectangle.width = 40;
###Xcode###
你可以把它看成是一个开发环境，就好像Visual Studio或者Netbeans或者SharpDevelop一样的玩意。你可以将Interface Builder认为是Visual Studio中用来画界面的那部分功能单独提出来的程序。
###Objective-C是什么？###
你可以把它认为是语法稍稍有点不一样的c语言。虽然第一眼望上去你可能会认为它是火星语，和你所认知的任何一种语言都不一样。  

简单列出一点差别：
####问题一：我在程序中看到大量的减号、中括号和NS****这种东西，他们是什么玩意儿？####
 1. 减号（或者加号）  
 减号表示一个函数、或者方法、或者消息的开始，怎么说都行。
 比如c#中，一个方法的写法可能是：
```c#
private void hello(bool ishello)
{
//OOXX
}
```
用Objective-C写出来就是
```
-(void) hello:(BOOL)ishello
{
//OOXX
}
```
挺好懂的吧？  
不过在Objective-C里面没有public和private的概念，你可以认为全是public。  
 
 
 