

## Integrated Online Trajectory Planning and Optimization in Distinctive Topologies
这篇文章最为详细地说明了TEB实现。



## Elastic Bands: Connecting Path Planning and Control

弹性带（EB）起源文章





## Kinodynamic Trajectory Optimization and Control for Car-Like Robots

这篇文章介绍较为详细地说明了TEB实现。





## Efficient Trajectory Optimization using a Sparse Model

时间弹性带算法使用g2o框架求解





摘要-“时间弹性带(TEB)”方法通过随后修改由全局规划器生成的初始轨迹来优化机器人轨迹。轨迹优化所考虑的目标包括但不限于总路径长度、轨迹执行时间、与障碍物的分离、通过中间路径点以及满足机器人的动力学、运动学和几何约束。TEB明确地考虑了运动的时空方面的动态约束，如有限的机器人速度和加速度。轨迹规划实时运行，使得TEB能够应对动态障碍物和运动约束。将“TEB问题”描述为一个尺度化的多目标优化问题。大多数目标是局部的，只与一小部分参数有关，因为它们只依赖于几个连续的机器人状态。这种局部结构产生一个稀疏的系统矩阵，从而允许使用快速有效的优化技术，如开源框架“g2o”来解决TEB问题。g2o稀疏系统解算器已成功地应用于VSLAM问题。本文描述了g2o框架在TEB轨迹修正中的应用和适应性。仿真和实际机器人实验结果表明，该方法具有良好的鲁棒性和计算效率。



### II. TIMED ELASTIC BAND
#### A. Definition of Timed Elastic Band (TEB)







<img src="/home/lichunhong/.config/Typora/typora-user-images/image-20200119165353121.png" alt="image-20200119165353121" style="zoom:80%;" />



#### B. Problem representation as a Hyper-Graph



![image-20200119173454890](/home/lichunhong/.config/Typora/typora-user-images/image-20200119173454890.png)





#### C. Control flow

<img src="/home/lichunhong/.config/Typora/typora-user-images/image-20200119173521625.png" alt="image-20200119173521625" style="zoom:80%;" />











