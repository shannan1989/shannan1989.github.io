---
layout: post
title:  "C#中的单例模式（Singleton Pattern）"
date:   2017-07-28 10:51:24 +0800
categories: CSharp
---

单例模式（Singleton Pattern），是一种常用的软件设计模式。

通过单例模式可以保证系统中一个类只有一个实例，即一个类只有一个对象实例。

单例模式最初的定义出现于《设计模式》（艾迪生维斯理, 1994）：“保证一个类仅有一个实例，并提供一个访问它的全局访问点。”

Java中单例模式定义：“一个类有且仅有一个实例，并且自行实例化向整个系统提供。”

显然，单例模式的要点有三个：

* 一是某个类 **只能有一个** 实例；
* 二是它必须 **自行创建** 这个实例；
* 三是它必须自行向整个系统提供这个实例。

因此需要用一种只允许生成类的唯一实例的机制，“阻止”所有想要生成对象的访问。

从具体实现角度来说，就是以下三点：

* 一是单例模式的类只提供 **私有的构造函数** ；
* 二是类定义中含有一个该类的 **静态私有对象** ；
* 三是该类提供了一个 **静态的公有函数** 用于创建或获取它本身的静态私有对象。

写法一：

	public class Logger
	{
	   private static Logger _logger = null;

	   private Logger()
	   {
	       //do something
	   }

	   public static Logger GetInstance()
	   {
	       if (_logger == null)
	       {
	           _logger = new Logger();
	       }
	       return _logger;
	   }

	   public void Log(object o)
	   {
	       Console.WriteLine(o);
	   }
	}

调用：

	Logger.GetInstance().Log("");

虽然次数很少，但如果每次请求引用时都要检查是否存在类的实例，将仍然需要一些开销。可以通过使用静态初始化解决此问题。

方法二：

	public class Logger
	{
	    private Logger()
	    {
	        //do something
	    }

	    static Logger()
	    {
	        Instance = new Logger();
	    }

	    public static Logger Instance
	    {
	        get;
	        private set;
	    }

	    public void Log(object o)
	    {
	        Console.WriteLine(o);
	    }
	}

调用：

	Logger.Instance.Log("");

