#1. 改完的*.dot截图
##1. 修改example2，让3个square模块变成2个
![](http://upload-images.jianshu.io/upload_images/3243156-37b7c894ff5e99c4.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
![](http://upload-images.jianshu.io/upload_images/3243156-17c111c825089a31.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
##2.修改example1，使其输出3次方数
![](http://upload-images.jianshu.io/upload_images/3243156-0e64f501f32071c4.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
![](http://upload-images.jianshu.io/upload_images/3243156-755d37c6b307cee8.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
***
#2.具体修改过程：
##Example1：
![](http://upload-images.jianshu.io/upload_images/3243156-1d9be29887db5827.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
将原本i=i*i改成i*i*i即可。原本结构中就只有1个square模块，如果要输出三次方数，直接修改i的赋值就行。
##Example2：
![](http://upload-images.jianshu.io/upload_images/3243156-e840df1c92a1ed84.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
个人测试发现直接改动这里的N值减少模块，从结果来看也是可以的，原本PPT中说改iterator的话，是不是把N变成N-1呢？
***
#3.实验感想：
以前在c++上很简单的一个程序，现在被分解成generator，consumer还有功能函数几个部分，还要用XML相连，看起来很麻烦，实际上将c++用汇编语言解析一下应该也是差不多的复杂了。
在几个c文件中，都有_init和_fire两个函数，前者初始化用，后者产生信号；都有一个元素len，规定了执行的次数，如果文件中的计数等于len，那么就会跳出循环，停止进程。
XML的分析：
process：实现的模块名字及其端口类型与名字；
sw_channel：通道的定义
connection：简单来说，process与channel之间一定会有一个connection，dot图上看起来是三个模块两条线，实际上一条线是由一个通道与两个connection组成的。