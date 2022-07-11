# Week 8 Assignment

## 1

First of all, the operating system will find a physical frame for the page to be swapped in.  After the physical frame is obtained, the processing sequence issues an I/O request to read the page from the swap space. Finally, when the slow operation is complete, the operating system updates the page table and retries the instructions. Retry will cause the TLB to miss, and then whenretry, the TLB will hit, and the hardware will be able to access the desired value。

## 2

7 0 1 2 0 3 0 4 2 3 0 3 2 1 2 0 1 7 0 1

### Optimal

![image-20220411232105662](/Users/wangxiequn/Library/Application Support/typora-user-images/image-20220411232105662.png)

8

### FIFO

![image-20220411232128846](/Users/wangxiequn/Library/Application Support/typora-user-images/image-20220411232128846.png)

10

### LRU

![image-20220411232105662](/Users/wangxiequn/Library/Application Support/typora-user-images/image-20220411232105662.png)

8



## 3

![image-20220412161528583](/Users/wangxiequn/Library/Application Support/typora-user-images/image-20220412161528583.png)

![image-20220412161544201](/Users/wangxiequn/Library/Application Support/typora-user-images/image-20220412161544201.png)

![image-20220412161556608](/Users/wangxiequn/Library/Application Support/typora-user-images/image-20220412161556608.png)

## 4

![image-20220412181641585](/Users/wangxiequn/Library/Application Support/typora-user-images/image-20220412181641585.png)

![image-20220412181651370](/Users/wangxiequn/Library/Application Support/typora-user-images/image-20220412181651370.png)

![image-20220412181708502](/Users/wangxiequn/Library/Application Support/typora-user-images/image-20220412181708502.png)
