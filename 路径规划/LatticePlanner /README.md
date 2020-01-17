



## Trajectory Planning for BERTHA -a Local, Continuous Method
摘要：本文在总结前人研究成果的基础上，提出了在完全自主完成柏莎-奔驰纪念路线103公里的车辆上进行轨迹规划的策略。我们提出一个由变分公式导出的局部连续方法。解的轨迹是一个目标函数的约束极值，该目标函数用于表达动态可行性和舒适性。静态和动态障碍物约束以多边形的形式合并。这些约束经过精心设计，以确保解收敛到单个全局最优解。





### II. RELATED WORK





#### A. Preliminaries

#### B. Objective function

代价函数组成：

<img src="/home/lichunhong/.config/Typora/typora-user-images/image-20200117194211159.png" alt="image-20200117194211159" style="zoom:80%;" />



#### C. Constraint functions

约束项：内部约束、外部约束

内部约束：最大曲率、最大加速度等

外部约束：物体碰撞

![image-20200117194511139](/home/lichunhong/.config/Typora/typora-user-images/image-20200117194511139.png)

进行物体碰撞检测，自车用多个圆表示，障碍物用多边形表示。



#### D. Building constraint polygons from sensor data





静态障碍物：left-right decision 根据简单的几何结构，将障碍物分配到左右两边

![image-20200117202900285](/home/lichunhong/.config/Typora/typora-user-images/image-20200117202900285.png)



动态障碍物：分为迎面车辆，划分在右侧；超车车辆，划分在左侧

移动障碍物预测：常速并且与右边界保持固定的距离。



#### E. Distance function

//TODO

基于优化的路径选择



![image-20200117205411907](/home/lichunhong/.config/Typora/typora-user-images/image-20200117205411907.png)







#### F. Re-planning scheme

![image-20200117204615577](/home/lichunhong/.config/Typora/typora-user-images/image-20200117204615577.png)





#### G. Constrained optimization

//TODO