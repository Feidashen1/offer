## 1.makefile 文件的作用是什么？
makefile文件由一组依赖关系和规则构成。每个依赖关系由一个目标（即将要创建的文件）和一组该目标所依赖的源文件组成。而规则描述了如何通过这些依赖文件创建目标。一般来说，目标是一个单独的可执行文件。

makefile 文件和 make 工具一起使用，用于控制工程项目的编译和链接，也可以用来编写手册页和程序的安装。make 工具用于解释执行 makefile 文件中的内容。makefile 文件中通常包含源文件和目标文件的依赖关系以及从源文件生成目标文件的规则。make 工具可以根据 makefile 判断哪些文件需要被重新编译，目标文件的构建顺序等。



链接：[https://www.cnblogs.com/qingergege/p/7832727.html](https://www.cnblogs.com/qingergege/p/7832727.html "make工具和makefile文件")



## 2.gdb三种调试方式
1）attach并调试一个已经运行的进程

确定需要进行调试的进程id运行gdb，输入attch pid，如：gdb 12345。
gdb将对指定进行执行如下操作：ptrace（PTRACE_ATTACH，pid，0,0）

2）运行并调试一个新的进程

运行gdb，通过命令行参数或file指定目标调试程序，如gdb ./test;
输入run命令，gdb执行下述操作：

通过fork()系统调用创建一个新进程，在新创建的子进程中调用ptrace(PTRACE_TRACEME，0,0,0）
，在子进程中通过execv()系统调用加载用户指定的可执行文件

3）远程调试目标主机上新创建的进程

gdb运行在调试机，gdbserver运行在目标机，通过二者之间定义的数据格式进行通信

## 3.gdb调试的基础--信号
gdb调试的实现都是建立在信号的基础上的，在使用参数为PTRACE_TRACEME或PTRACE_ATTACH的ptrace系统调用建立调试关系后，交付给目标程序的任何信号首先都会被gdb截获。

因此gdb可以先行对信号进行相应处理，并根据信号的属性决定是否要将信号交付给目标程序。

链接：[https://blog.csdn.net/u012658346/article/details/51159971](https://blog.csdn.net/u012658346/article/details/51159971 "https://blog.csdn.net/u012658346/article/details/51159971")

## 4.gdb的功能
四个方面的功能：
1、按照自定义的方式启动运行需要调试的程序。

2、可以使用指定位置和条件表达式的方式来设置断点。

3、程序暂停时的值的监视。

4、动态改变程序的执行环境。

## 5.coredump
Coredump 叫做核心转储，它是进程运行时在突然崩溃的那一刻的一个内存快照。
操作系统在程序发生异常而异常在进程内部又没有被捕获的情况下，会把进程此刻内存、寄存器状态、运行堆栈等信息转储保存在一个文件里，该文件也是二进制文件。

