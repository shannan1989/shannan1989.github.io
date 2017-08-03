---
layout: post
title:  "macOS中如何直接运行 Python 脚本？"
date:   2017-08-03 16:04:24 +0800
categories: Python
---

1、将代码文件首行改为：

	#!/usr/bin/env python 

2、将 python 脚本的扩展名改为 .command

	mv test.py test.command  

3、为脚本添加可执行权限：

	chmod +x test.command  

4、在 Finder 中双击文件即可运行。

注意：双击后会打开终端，脚本初始的运行路径是用户的根目录(即~)。

如果脚本中有相对路径的操作，脚本运行的时候结果会与预期相左。

可将如下代码加到原有逻辑代码之前：

	import os

	path = os.path.dirname(sys.argv[0])  

	os.chdir(path)  

这段代码做的是：

首先获取到该脚本所在的物理路径，再将运行路径切换到该路径。
