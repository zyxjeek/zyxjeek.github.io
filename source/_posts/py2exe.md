---
title: py2exe使用教程
date: 2023-3-25 15:34
tags: python
---

py2exe是一个方便的工具，可以将Python程序转化为可以再Windows上直接运行的exe文件，适用于将Python程序分享给没有安装Python解释器用户。下面由我带大家了解一下py2exe的使用。

## 3.26日更新：推荐使用pyinstaller！！！

这两天笔者又发现了另一个python包，叫做pyinstaller，真的超好用。

安装：`pip install pyinstaller`

使用：`pyinstaller --onefile main.py`

众所周知，py2exe打包的程序需要带着`dist`文件夹一起执行，而pyinstaller直接提供了`--onefile`这一选项！打包后，`dist`文件夹里的exe可以单独使用，其余的文件可以直接删除！

而且，pyinstaller不需要编写`setup.py`，只需1个命令就可以搞定。

它的缺点是不能打包更复杂的程序，比如我曾经写的外星人游戏。但是新手时期的控制台程序完全可以用它搞定。

## 一、 安装py2exe

1. 使用Win+R快捷键打开运行窗口，输入cmd，回车。

![image-20230325143417881](https://i.postimg.cc/R0k6XV5w/image.png)

2. 检查Python和pip版本（版本可能与我的不同，只要不报错就可以）

   ```
   C:\Users\yixun>python --version
   Python 3.10.5
   
   C:\Users\yixun>pip --version
   pip 22.0.4 from C:\Users\yixun\AppData\Local\Programs\Python\Python310\lib\site-packages\pip (python 3.10)
   ```

3. 安装py2exe：`pip install py2exe`

## 二、使用py2exe

1. 首先将cmd切换到你的文件夹里，比如`cd C:\Users\yixun\Desktop\Code`。安装了Windows终端的读者也可以在文件夹里右击，然后这样：

   ![image-20230325144404474](https://i.postimg.cc/kM8FrzTn/image.png)

2. 创建一个测试用的Python程序，比如经典的废话程序“身高计算器”：

   ```python
   print("你的身高是：" + input("请输入你的身高："))
   input()   #防止输出太快窗口直接关闭，建议每个要转成exe的程序都添加这一句话
   ```

   可以命名为`main.py`

3. 接下来，创建一个新的Python程序，可以命名为`setup.py`

   ```python
   from distutils.core import setup
   import py2exe
   
   sys.argv.append('py2exe')
   setup(console=["main.py"]) # 与你的程序文件名匹配
   ```

   注意，所有命名都不是强制性的，可以随意更改。

4. 双击运行`setup.py`

5. 这会生成一个名叫`dist`的子目录，注意如果要把exe分享给别人，dist目录要一起分享。

6. 打开dist目录中的main.exe，成功运行，最后按Enter可以退出程序。

> 如有疑问，请联系yixun2010@outlook.com


---

The END
