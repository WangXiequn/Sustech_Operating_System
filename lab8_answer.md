### 一个进程有多少个mm_struct? mm_struct的作用是什么？

1 个。用来管理vma_struct 

###  vma_struct的作用是什么？

vma_struct结构体描述一段连续的虚拟地址

###  什么情况下会出触发缺页中断？

当mmu未能找到虚拟地址对应的物理地址

###  major page fault是如何处理的？在实验代码中对应哪一段？

os重新分配物理页面。把原来的物理地址内容放到外部交换区。然后将改内容写成pte.最后建立物理叶与虚拟地址的映射。

![image-20220408151237200](/Users/wangxiequn/Library/Application Support/typora-user-images/image-20220408151237200.png)

### swap_in和swap_out分别发生在什么时候？（选做，建议做）

swap_in 换入的时候，我们新分配一个物理页面，根据虚拟地址对应的pte在硬盘上找到对应的位置（这里用的 时简单的偏移实现），将硬盘的内容换入到新分配的页面。

swap_out 换出的时候，首先根据替换算法找到要被换出的那一个page，称为victim。接着找到victim对应的虚拟 地址，根据这个虚拟地址构造一个可以放在硬盘上的位置，将victim换出。同时在更改victim对应的页 表项，将硬盘对应的位置放入到victim的页表项中，最后释放掉对应的物理页面。