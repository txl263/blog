---
published: true
layout: default
title: Mac OS Development - 2 - Xcode Hello World
---

###Remember
 - creating a metod: -(returnType) methodName:(arg)a;
 - calling a method: [objectName methodName:a];
 - Accessing objects using dot
 ex: Rectangle.width = 40;
###Xcode
你可以把它看成是一个开发环境，就好像Visual Studio或者Netbeans或者SharpDevelop一样的玩意。你可以将Interface Builder认为是Visual Studio中用来画界面的那部分功能单独提出来的程序。
###Objective-C是什么？
你可以把它认为是语法稍稍有点不一样的c语言。虽然第一眼望上去你可能会认为它是火星语，和你所认知的任何一种语言都不一样。  

简单列出一点差别：
####问题一：我在程序中看到大量的减号、中括号和NS****这种东西，他们是什么玩意儿？
 - 减号（或者加号）  
 
 减号表示一个函数、或者方法、或者消息的开始，怎么说都行。
 比如c#中，一个方法的写法可能是:
 
    private void hello(bool ishello)
    {
    //OOXX
    }
用Objective-C写出来就是

	-(void) hello:(BOOL)ishello
	{
	//OOXX
	}
挺好懂的吧？  
不过在Objective-C里面没有*public*和*private*的概念，你可以认为全是*public*。    
而用加号的意思就是其他函数可以直接调用这个类中的这个函数，而不用创建这个类的实例。
 - 中括号
 
 中括号可以认为是如何调用你刚才写的这个方法，通常在Objective-C里说“消息”。  
比如C#里你可以这么写:`this.hello(true);`  
在Objective-C里，就要写成:```[self hello:YES];```  
 
 - NSxxxx  
 
  老乔当年被人挤兑出苹果，自立门户的时候做了个公司叫做NextStep，里面这一整套开发包很是让一些科学家们喜欢，而现在Mac OS用的就是NextStep这一套函数库。  
  这些开发NextStep的人们比较自恋地把函数库里面所有的类都用NextStep的缩写打头命名，也就是NS****了。比较常见的比如：  
NSLog  
NSString  
NSInteger  
NSURL  
NSImage  
…  
你会经常看到一些教学里面会用到：  

``NSLog (@"%d",myInt);``    
这句话主要是在console里面跟踪使用，你会在console里面看到myInt的值（在XCode里面运行的时候打开dbg窗口即可看到）。而我们在其他开发环境里面可能会比较习惯使用MessageBox这种方式进行调试。  
你还可以看到其他名字打头的一些类，比如CF、CA、CG、UI等等，比如  
CFStringTokenizer 这是个分词的东东  
CALayer 这表示Core Animation的层  
CGPoint 这表示一个点  
UIImage 这表示iPhone里面的图片  
CF说的是Core Foundation，CA说的是Core Animation，CG说的是Core Graphics，UI说的是iPhone的User Interface……还有很多别的，等你自己去发掘了。   
####问题二、#import、@interface这类玩意说的是什么？

 - #import  
 
 你可以把它认为是#include，一样的。但是最好用#import，记住这个就行了。  
 - @interface等等  
 
 比如你在c#中写一个抓孩子类的定义：
 
	public class Kids : System
	{
	private string kidName=”mykid”;
	private string kidAge=“15”;
	private bool isCaughtKid()
	{
	return true;
	}
	}
当然，上面的写法不一定对，就是个用于看语法的举例。  
在Objective-C里就得这么写：  
先写一个kids.h文件定义这个类：  

	@interface Kids: NSObject {
	NSString *kidName;
	NSString *kidAge;
	}
	-(BOOL) isCaughtKid:;
	@end
再写一个kids.m文件实现：  

	\#import “kids.h”
	@implementation Kids
	-(void) init {
	kidName=@”mykid”;
	kidAge=@”15”;
	}
	-(BOOL) isCaughtKid:{
	return YES;
	}
	@end
这个写法也不一定对，主要是看看语法就行了。-_-b


