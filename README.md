#README.md

##Description
The distributed operation layer (DOL) is a software development framework to program parallel applications. The DOL allows to specify applications based on the Kahn process network model of computation and features a simulation engine based on systemC. Moreover, the DOL provides an XML-based specification format to describe the implementation of a parallel application on a multi-processor systems, including binding and mapping.

![](http://upload-images.jianshu.io/upload_images/3243156-1d22f956a3996da2.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)框架图

##How to install
###1.安装vmware与Ubuntu。
这个倒是上学期学习操作系统这门课时就早已搞好的东西了呢。
###2.安装必要的环境
$ sudo apt-get update
$ sudo apt-get install ant（基于Java的build工具）
$ sudo apt-get install openjdk-7-jdk
$ sudo apt-get install unzip（解压）
###3.解压准备好的文件
####新建dol的文件夹
$ mkdir dol
####将dolethz.zip解压到 dol文件夹中
$ unzip dol_ethz.zip -d dol
####解压systemc
$ tar -zxvf systemc-2.3.1.tgz
###4.编译systemc
####解压后进入systemc-2.3.1的目录下
$ cd systemc-2.3.1
####新建一个临时文件夹objdir
$ mkdir objdir
####进入该文件夹objdir
$ cd objdir
####运行configure
$ ../configure CXX=g++ --disable-async-updates
####编译
$ sudo make install
####记录当前的工作路径

![](http://upload-images.jianshu.io/upload_images/3243156-015b1549cd7cdbc0.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)输入pwd后得到路径

###5.编译DOL
####进入刚刚dol的文件夹
$ cd ../dol
####修改build_zip.xml文件
找到下面这段话，就是说上面编译的systemc位置在哪里，把YYY改成上页pwd的结果
```
<property name="systemc.inc" value="YYY/include"/>
<property name="systemc.inb" value-"YYY/lib-linux/libsystemc.a">
```
![](http://upload-images.jianshu.io/upload_images/3243156-817624efd870e8b5.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

####编译（成功则显示build successful）
####试运行第一个例子
进入build/bin/mian路径下
$ cd build/bin/main
然后运行第一个例子
$ ant -f runexample.xml -Dnumber=1

![例子1截图](http://upload-images.jianshu.io/upload_images/3243156-261312c8752794de.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
###6.用XDOT打开.dot文件查看

![.dot文件](http://upload-images.jianshu.io/upload_images/3243156-00cd0dd3562edff7.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
##实验感想（10.9）
配置实验永远是很舒服的www
只要按照ppt的指示输好指令，等待系统跑程序，不用一会就可以看到想要的结果。
但是就像操作系统一样，一旦深入到linux里，后面的实验估计会很头疼。
意外地我并没有碰到很多报错，然后群里那些问题我也不知道为什么会有这种错误，可以说意外地一帆风顺，傻人有傻福吧。
也第一次接触了markdown，也就明白上学期数值分析的TA为什么丢到群里的作业是一个.md格式的文件了。markdown的语法，其实很简单，相对于最近愈发加大难度的html作业已经算是福利了。