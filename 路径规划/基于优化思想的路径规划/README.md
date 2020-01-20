# 基于优化的轨迹规划

## Optimization-Based Collision Avoidance

摘要：利用凸优化的强对偶性，提出了一种将不可微碰撞避免约束转化为光滑非线性约束的新方法。我们关注的是一个控制对象，其目标是在n维空间中移动时避开障碍物。所提出的重构不引入近似，并且适用于一般的障碍物和受控对象，它们可以表示为凸集的并集。我们将我们的结果与符号距离的概念联系起来，符号距离在传统的轨迹生成算法中得到了广泛的应用。我们的方法可以应用于一般的导航和轨迹规划任务，并且平滑特性允许使用通用的基于梯度和Hessian的优化算法。最后，在无法避免碰撞的情况下，我们的框架允许我们找到“至少有吸引力”的轨迹，以穿透力来衡量。我们证明了我们的框架在四直升机导航和自动泊车问题上的有效性，并且我们的数值实验表明，所提出的方法能够在紧环境下实现基于实时优化的轨迹规划问题。我们实现的源代码见https://github.com/XiaojingGeorgeZhang/OBCA。









## Integrated Online Trajectory Planning and Optimization in Distinctive Topologies
这篇文章**最为**详细地说明了TEB实现。

参考：

[1] http://www.pianshen.com/article/4783688865/

## Elastic Bands: Connecting Path Planning and Control

弹性带（EB）起源文章





## Kinodynamic Trajectory Optimization and Control for Car-Like Robots

这篇文章介绍**较为**详细地说明了TEB实现。





## Efficient Trajectory Optimization using a Sparse Model

**时间弹性带算法使用g2o框架求解**





摘要-“时间弹性带(TEB)”方法通过随后修改由全局规划器生成的初始轨迹来优化机器人轨迹。轨迹优化所考虑的目标包括但不限于总路径长度、轨迹执行时间、与障碍物的分离、通过中间路径点以及满足机器人的动力学、运动学和几何约束。TEB明确地考虑了运动的时空方面的动态约束，如有限的机器人速度和加速度。轨迹规划实时运行，使得TEB能够应对动态障碍物和运动约束。将“TEB问题”描述为一个尺度化的多目标优化问题。大多数目标是局部的，只与一小部分参数有关，因为它们只依赖于几个连续的机器人状态。这种局部结构产生一个稀疏的系统矩阵，从而允许使用快速有效的优化技术，如开源框架“g2o”来解决TEB问题。g2o稀疏系统解算器已成功地应用于VSLAM问题。本文描述了g2o框架在TEB轨迹修正中的应用和适应性。仿真和实际机器人实验结果表明，该方法具有良好的鲁棒性和计算效率。



### II. TIMED ELASTIC BAND
#### A. Definition of Timed Elastic Band (TEB)







<img src="/home/lichunhong/.config/Typora/typora-user-images/image-20200119165353121.png" alt="image-20200119165353121" style="zoom:80%;" />



#### B. Problem representation as a Hyper-Graph



![image-20200119173454890](/home/lichunhong/.config/Typora/typora-user-images/image-20200119173454890.png)





#### C. Control flow

<img src="/home/lichunhong/.config/Typora/typora-user-images/image-20200119173521625.png" alt="image-20200119173521625" style="zoom:80%;" />







## G2o: A general framework for graph optimization

摘要-机器人学和计算机视觉中的许多常见问题，包括各种类型的同时定位和映射（SLAM）或束平差（BA），可以**用图形表示的误差函数的最小二乘优化来表达**。本文描述了这些问题的一般结构，并提出了**G2O，一个开源的C++框架**，用于**优化基于图的非线性误差函数**。我们的系统被设计成很容易扩展到各种各样的问题，一个新的问题通常可以在几行代码中指定。当前的实现为SLAM和BA的几种变体提供了解决方案。我们提供了对大量真实世界和模拟数据集的评估。结果表明，虽然g2o是通用的，但它的性能可以与针对特定问题的现有方法的实现相媲美。





g2o的本质：g2o是一个算法集的C++实现，而并不是在算法理论上的创新，即根据前人求解非线性最小二乘的理论，根据具体的问题，选用最合适的算法。

它是一个平台，你可以加入你自己的线性方程求解器，编写自己的优化目标函数，确定更新的方式。g2o的作者说Guassian-Newton和Levenberg-Marquardt方法比较naive，但是g2o的本质就是这些算法的实现。事实上，g2o iSAM SPA和 sSPA等非线性优化算法只是在非线性问题线性化时处理得不一样，在线性化后要求解线性方程都是利用了已有的linear solver库来求解，如 CSparse CHOLMOD PCG等，他们都需要依靠Eigen这个线性代数库。

g2o的用途：很多机器人的应用如SLAM（同步定位与制图）还有计算机视觉中的光束优化（bundle adjustment 都会涉及到最小化非线性误差函数的问题。这类应用中，**非线性误差函数可以用图(graph)的形式来表征**。整个问题的求解就是要找到最符合观测量的相机参数或机器人状态。

参考：

[1] https://blog.csdn.net/zhongjin616/article/details/15498779



