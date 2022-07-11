1. 详细描述do_fork的函数调用过程，具体请包括do_fork内部调用（跳转至）了哪些函数，调用过程是怎样的，每个函数（包括do_fork）的作用是什么。请不要直接粘贴代码。

   do_fork 函数是将当前进程复制一遍，用来创建新的进程。

   调用了alloc_proc，setup_stack，copy_mm，copy_thread，list_add，wake_up函数


   调用alloc_proc来分配proc_struct（即线程）

   

   调用setup_kstack为子进程分配内核堆栈

   利用copy_mm函数来复制或者共享内存管理（由clone flag决定）

   list_add把进程加入链表，

   Wakeup_proc 来唤醒进程

   返回值设为线程id.

   

   

2. 详细描述schedule的函数调用过程，具体请包括 schedule内部调用（跳转至）了哪些函数，调用过程是怎样的，每个函数（包括schedule）的作用是什么。请不要直接粘贴代码

调用了list_next,proc_run,local_intr_restore ,local_intr_save方法

schedule是当调度时，将当前进程放在队尾，然后运行队首的进程（能运行的，）

list_next是用来遍历进程

proc_run即运行进程

local_intr_save,local_intr_restorce用来保存（新进程运行前）与恢复当前进程（新进程运行结束后）。