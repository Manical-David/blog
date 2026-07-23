---
title: Microsoft Visual Studio安装程序项目
date: 2025-08-16 22:11:25
tags: visual studio
categories: 开发工具
---
> Notice
This is an archived post.
这是一篇留档文章

MSVS是一个多功能集成的开发软件，它能开发许多像游戏、学习软件之类的，像人人知晓的Microsoft Office也是用它开发的。但是开发完软件，需要一个安装程序来将你开发的程序打包，以让更多人能使用你的软件。
可是问题来了，VS刚安装完之后并没有安装程序组件，只能用C++的MSIX进行编程，你是想把手打烂还效果不好的还是用鼠标一拖就打包好的呢？当然很多人选择后者，但是有一些人为了界面美观的强迫症而选择了前者，我有什么办法呢？~~无语(ˉ▽ˉ；)...~~
好了，废话不多说，直接开始！
 ## 第一步，安装程序组件下载
 （如果Microsoft Visual Studio Install Project这个组件已经下载好了的话，跳过第一步）
 我们先启动VS程序（本人使用VS2022，这个版本好用一点，其他版本也可以，但必须是2013年及以上年版的）
![在这里插入图片描述](https://i-blog.csdnimg.cn/blog_migrate/40c4245577a8ed0343c9f97c5f525458.png#pic_center)
 然后随便点开一个自己的项目
 ![在这里插入图片描述](https://i-blog.csdnimg.cn/blog_migrate/39105fd8c243694137cef09fe038362c.png#pic_center)
进入编辑界面后，点击扩展>管理扩展
![在这里插入图片描述](https://i-blog.csdnimg.cn/blog_migrate/cad48960766e45afc8f86f4bc1ee81da.png#pic_center)
之后可以看见这个界面
![在这里插入图片描述](https://i-blog.csdnimg.cn/blog_migrate/bd7e988bff3fb95cf43fea9e6640bed3.png#pic_center)
我们再搜索框里面输入：Microsoft Visual Studio install Project
![在这里插入图片描述](https://i-blog.csdnimg.cn/blog_migrate/32ba6eadcdcb864f40f66b50bccec787.png#pic_center)
![在这里插入图片描述](https://i-blog.csdnimg.cn/blog_migrate/39ad2d874d753ad73b48ccb2e318d6cb.png#pic_center)
之后等个一两秒，然后关闭VS，会看见一个白色的不明窗口，千万不要关掉，因为一旦关掉，你就要重新执行以上步骤，重新安装。

## 第二步，检查安装
安装完了之后，重新打开管理扩展界面，会变成如图所示：
![在这里插入图片描述](https://i-blog.csdnimg.cn/blog_migrate/28aba717c66fbcb3c57fd3debbeefcd4.png#pic_center)
之后，就可以开始使用了！o(·￣▽￣)ブ
## 第三步，使用安装程序
安装无误了之后，就可以安装使用了。我们重新进入VS，在“创建新项目”窗口搜索：“Setup Project”，然后点击如下图所示：![在这里插入图片描述](https://i-blog.csdnimg.cn/blog_migrate/de69b5f1079e7dea530c4c40445ba9a6.png#pic_center)
完成上述操作后，就来到了编辑界面，可以看到编辑界面和平时打代码的界面不一样
![在这里插入注释](https://i-blog.csdnimg.cn/blog_migrate/4116e67e2675348d3edfe29d508d0e3f.png#pic_center)


这里大部分都是文件夹，这里我们先打开“Application Folder”文件夹，然后将要打包的文件拖进去![在这里插入图片描述](https://i-blog.csdnimg.cn/blog_migrate/bd42c0a4a80f47a43ac15c81fa7c32d7.png#pic_center)
然后呢，这里，我们想要在桌面安装一个快捷方式，或者是在开始菜单里面添加这个程序的快捷方式，这样我们在打开程序的时候才能更方便。

这里，生成这个安装程序，我们就不能用调试运行了，而是需要生成栏 —— 生成 这个选项来进行安装程序的生成。
### 添加到桌面
我们看到有一个"User's Desktop"的文件夹，我们点进去，把先前创建好的快捷方式托进去，就可以在桌面也出现这个程序的快捷方式了。
### 添加到开始窗口
我们看到有一个叫做“![在这里插入图片描述](https://i-blog.csdnimg.cn/blog_migrate/ef16f6f2be4a5eb9b6807efbdc73842a.png)的文件夹，我们点进去，把先创建好的快捷方式托进去就行了。

---