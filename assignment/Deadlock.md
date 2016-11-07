# Deadlock死锁实验

## 实验内容

### 本次实验就是按照课上给出的代码，在LINUX系统或者WINDOWS系统之下运行，修改代码之中的可执行文件中的循环次数，运行之后，观察死锁的情况截图，并分析。

### 编译运行

#### 1.代码写好之后，先执行javac Deadlock.java,之后就会看到文件夹之中多出三个.class文件，然后把deadlock文件添加可执行权限，在命令行之中输入sudo chmod +x deadlock。然后执行./deadlock执行该文件。
![1](https://github.com/Lawrrencelrm/ES2016_14353204/raw/master/Screenshots/deadlock3.png)



#### 2.刚开始，我是一直再修改Deadlock.java之中的count值，改到如下图所示的大小，但还是没有产生死锁，后来就直接修改deadlock循环条件之中c的上限值为10000。这两种方法更改的原理一样，都是为了让两个线程刚好达到死锁的条件。
![2](https://github.com/Lawrrencelrm/ES2016_14353204/raw/master/Screenshots/deadlock1.png)
![3](https://github.com/Lawrrencelrm/ES2016_14353204/raw/master/Screenshots/deadlock2.png)


#### 3.产生死锁的截图如下：
![4](https://github.com/Lawrrencelrm/ES2016_14353204/raw/master/Screenshots/deadlock4.png)



### 死锁分析:

#### 在主线程中，线程t调用函数start()之后，调用函数run()一直在后台运行，然后经过一个while循环，a调用函数methodA（B b）申请B的资源并调用，run()函数中的b.methodB(A a)与之类似。当这两个线程在经过数次循环之后，时间差刚好抵消掉，他们两个都是占有自己本身所属的类A|B的资源，然后申请相应的B|A的资源，但是由于关键字synchronized限定当一个类的一个资源被某一个线程占用，其他的资源就不可以被另外的线程申请到，在这种情况下，两个线程分别占有一个资源又申请对方所占用的资源，但是对方本身占用资源又必须等到申请到资源之后才可以释放，就会产生死锁。

### 死锁产生的必要条件

#### 1.互斥：一个资源每一次只能被一个线程使用

#### 2.占有并等待：一个线程因请求资源而被阻赛时，对已获得的资源保持不放，并请求另外一个资源。

#### 3.非抢占：线程已获得的资源，在未使用完之前，布恩那个强行剥夺。

#### 4.循环等待：若干进程之间形成一种头尾相接的循环等待资源关系。



### 实验感想：

#### 重新温习了之前所学习的有关于进程死锁的问题，与我们这次的实验还是一样的。

#### 我这次实验是在虚拟机LINUX系统之下做的，因此，知道了有关于可执行文件的问题，以及使用chmod给文件加权限，同时，知道如何在命令行编译运行java文件。







