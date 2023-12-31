# Using capability to implement memory bounds checking
Wuyang Chung, wy-chung@outlook.com

Sep. 4, 2023

You can see the video of this presentation on [YouTube](https://www.youtube.com/watch?v=y63Ssb-rXZg&list=PL5d-EWnuoeCpW6n0K4Gdjk0pp5TSS0RKv&index=1&ab_channel=wy-chung).

Generally speaking there are two ways to do memory bounds checking, the object-based approach and the pointer-based approach. 
Each has its advantages and disadvantages. In this article I propose a capability-based approach to do memory bounds checking.

The table below shows the comparison of these approaches.

![image](pics/comparison.png)

Below is the format of the pointer for capability-based approach.

![image](pics/pointer_format.png)

The advantages of capability-based approach are:
* The pointer is smaller than the fat pointer based approach
* The overhead to get the object metadata is very low
* When doing memcpy, there is no need to propagate the metadata for the pointers in the buffer since the metadata are in a spearate table
* It can detect temporal safety violations by using capability revocation
* It supports principle of intentional use
* It supports principle of exclusive thread local data
