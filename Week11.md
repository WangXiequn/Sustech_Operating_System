# Week11

## EX0. CPU Scheduling



| Process | Estimated CPU Cost | Arrives | Priority |
| ------- | ------------------ | ------- | -------- |
| A       | 4                  | 1       | 1        |
| B       | 1                  | 2       | 2        |
| C       | 3                  | 5       | 3        |
| D       | 2                  | 4       | 4        |

| Time                  | HRRN              | FIFO/FCFS         | RR                 | SJF               | Priority           |
| --------------------- | ----------------- | ----------------- | ------------------ | ----------------- | ------------------ |
| 1                     | A                 | A                 | A                  | A                 | A                  |
| 2                     | A                 | A                 | B                  | A                 | A                  |
| 3                     | A                 | A                 | A                  | A                 | A                  |
| 4                     | A                 | A                 | D                  | A                 | A                  |
| 5                     | B                 | B                 | C                  | B                 | B                  |
| 6                     | D                 | D                 | A                  | D                 | C                  |
| 7                     | D                 | D                 | D                  | D                 | C                  |
| 8                     | C                 | C                 | C                  | C                 | C                  |
| 9                     | C                 | C                 | A                  | C                 | D                  |
| 10                    | C                 | C                 | C                  | C                 | D                  |
| Avg. Turn-around Time | （4+4+4+8）/4 = 5 | （4+4+4+8）/4 = 5 | （9+1+4+8）/4 =5.5 | （4+4+4+8）/4 = 5 | (4+4+4+7)/4 = 3.75 |

## EX1

The design id is quit simple, just follow the way to do the syscall and finally change the attribute priority.

![image-20220507171700615](/Users/wangxiequn/Library/Application Support/typora-user-images/image-20220507171700615.png)

Change to run ex1

![image-20220507171805395](/Users/wangxiequn/Library/Application Support/typora-user-images/image-20220507171805395.png)

![image-20220507171725824](/Users/wangxiequn/Library/Application Support/typora-user-images/image-20220507171725824.png)

Add syscall

![image-20220507171909862](/Users/wangxiequn/Library/Application Support/typora-user-images/image-20220507171909862.png)

change priority

![image-20220507171943550](/Users/wangxiequn/Library/Application Support/typora-user-images/image-20220507171943550.png)

The change of .h file is trivial and I think it is not necessary to show.

![image-20220507171256691](/Users/wangxiequn/Library/Application Support/typora-user-images/image-20220507171256691.png)



## EX2



![image-20220507192146481](/Users/wangxiequn/Library/Application Support/typora-user-images/image-20220507192146481.png)

![image-20220507192154638](/Users/wangxiequn/Library/Application Support/typora-user-images/image-20220507192154638.png)

## EX3



![image-20220507223729380](/Users/wangxiequn/Library/Application Support/typora-user-images/image-20220507223729380.png)

![image-20220507224024499](/Users/wangxiequn/Library/Application Support/typora-user-images/image-20220507224024499.png)

![image-20220507224156010](/Users/wangxiequn/Library/Application Support/typora-user-images/image-20220507224156010.png)

![image-20220507224202084](/Users/wangxiequn/Library/Application Support/typora-user-images/image-20220507224202084.png)

![image-20220507224818646](/Users/wangxiequn/Library/Application Support/typora-user-images/image-20220507224818646.png)

![image-20220507224933474](/Users/wangxiequn/Library/Application Support/typora-user-images/image-20220507224933474.png)

The good is like a priority to set.  For init, set to 6

We close the clock and change pick function.

![image-20220507224535371](/Users/wangxiequn/Library/Application Support/typora-user-images/image-20220507224535371.png)

For every pick, choose the biggest value of good.
