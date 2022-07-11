## Practice 10

## 1. 代码中通过何种方式从S mode 进入U mode？

user_main执行时调用exec()，将当前进程资源替换为新程序。同时，通过更改status的SPP位使得中断 返回时返回至Umode；

## 2.代码中用户进程调用系统调用的过程是怎样的？

使用`ecall`指令从U mode进入S mode。在S mode调用OpenSBI提供的M mode接口。当时我们用`ecall`进入了M mode, 剩下的事情就交给OpenSBI来完成，然后我们收到OpenSBI返回的结果。

但是ecall会被封装成系统调用的函数。

总体来说，用户进程通过封装的函数调用函数，然后中断进入内核态，再等待返回。