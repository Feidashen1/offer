# 1.makefile 文件的作用是什么？
makefile文件由一组依赖关系和规则构成。每个依赖关系又一个目标（即将要创建的文件）和一组该目标所依赖的源文件组成。而规则描述了如何通过这些依赖文件创建目标。一般来说，目标是一个单独的可执行文件。

makefile 文件和 make 工具一起使用，用于控制工程项目的编译和链接，也可以用来编写手册页和程序的安装。make 工具用于解释执行 makefile 文件中的内容。makefile 文件中通常包含源文件和目标文件的依赖关系以及从源文件生成目标文件的规则。make工 具可以根据makefile 判断哪些文件需要被重新编译，目标文件的构建顺序等。



链接：[https://www.cnblogs.com/qingergege/p/7832727.html](https://www.cnblogs.com/qingergege/p/7832727.html "make工具和makefile文件")


