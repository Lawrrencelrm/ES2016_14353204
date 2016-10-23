# 实验二

## ·修改example2,让3个square模块变成两个

### （1）example2 DOL图如下图所示：
![1](https://github.com/Lawrrencelrm/ES2016_14353204/raw/master/Screenshots/dol_1.png)
### （2）从该dot图之中，可以看到从square到channel的连线有3组，从generator到square,square到consumer则是分别有一组，example2.xml文件之中，表示迭代次数的是N,也就是square函数被应用的次数。

###   （3）改example2.xml文件中N的大小即可（进入到example2.xml文件所在的文件夹，在命令行中输入sudo gedit example2.xml
![2](https://github.com/Lawrrencelrm/ES2016_14353204/raw/master/Screenshots/dol_2.png)
### （4）编译，运行：输入命令sudo ant –f build_zip.xml all编译，而后输入测试命令：Sudo ant -f runexample.xml -Dnumber=2,可以从终端看到测试结果如下图。
![3](https://github.com/Lawrrencelrm/ES2016_14353204/raw/master/Screenshots/dol_3.png)

## ·修改example1,让其输出三次方数

### 这个比较简单，只需要修改函数square.c文件，使得i=i*I变成i=i*i*I。不过，这道题目在编译测试的时候，需要把原本编译测试生成的bin/main/example1文件夹删除掉，不然看不到修改之后的结果。

### 最后的结果如下图所示：
![4](https://github.com/Lawrrencelrm/ES2016_14353204/raw/master/Screenshots/dol_4.png)
## ·实验感想

### 通过这两个DOL实例，我自己对于DOL内部定义的模块以及模块之间的连接有了一定了解，怎么说，没有自己想象中那么复杂，从生成的DOL图中可以很清晰的看到他们之间的连接以及构架。











/















