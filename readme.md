in this repository I share a zynq-vdma driver I used in stereo vision ,and an demo app that utilize this driver . 
I used to have trouble with this driver,and had spend sometime to figure it out。it might be not a standard way, but it works well in this case.
I hope this can help some FPGA guys . if there is something wrong, pls kindly correct me .

note that the main job this app does is as follows : 
1. read rectified images , (this FPGA bit stream file is used to test KITTI dataset, so the rectify module is commended out in verilog HDL project)
2. load it to DDR memory .
3. triger the stereo IP core in FPGA side to generate depth image, depending whether you press 'c' or 'g', it shows color or gray depth image respectively

![alt text](https://raw.githubusercontent.com/brianwchh/zynq-stereo-driver-and-app/master/ipblock/ipblock.png)


## demo videos : 

https://www.youtube.com/watch?v=ESit3O7KgRc

https://www.youtube.com/watch?v=6NAkgadpmGY


## credit goes to many people who has shared their knowledge . 
共勉一下：勤学习，多涨薪，追房价（按现阶段的物价，动动指头，先赚他个4-6万/月吧，哈哈^_^，开心就好）。为社区尽一点微薄之力，帮助更多的创客。


blog : 有时间写下简单的介绍
	1. 在kernel space申请一段连续的内存。
	2. 把fb的物理地址写入vdma的寄存器
	3. 在user space获得fb的虚拟地址
