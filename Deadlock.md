#截图
![](http://upload-images.jianshu.io/upload_images/3243156-8f7a0794832a1129.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
![](http://upload-images.jianshu.io/upload_images/3243156-40602a215cff91e9.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
#死锁4条件
互斥条件： 某时刻某资源每次只能被一个进程使用
占有并等待条件：一个进程至少占有一个资源，并等待另一资源，因请求资源而阻塞时，对已获得的资源保持不放
非抢占条件:进程已获得的资源，在末使用完之前，不能强行剥夺；资源不能抢占，只能在进程完成后自动释放。
循环等待条件:若干进程之间形成一种头尾相接的循环等待资源关系，资源被下一个进程占有，循环。

#死锁原因
runnable函数中，run函数输出(Inside B.last())，而又有另一个线程进行着计数，计数到达count结束时输出(Inside A.last())。
我们知道，当一个线程访问object的一个synchronized(this)同步代码块时，其他线程对object中所有其它synchronized(this)同步代码块的访问将被阻塞。
现在后台的线程被调度到运行t.start()时才会开始运行run里的代码，即输出(Inside B.last())，而同时计数结束时就会输出(Inside A.last())，如果在计时结束时，刚好两个synchronized代码块都要运行，那么就会由于互斥性互不相让，程序无法输出，产生了死锁。