### 1. 官方demo包



```
wget http://db3.ertl.jp/autoware/sample_data/sample_moriyama_data.tar.gz
wget http://db3.ertl.jp/autoware/sample_data/sample_moriyama_150324.tar.gz

```

官方示例包的网上讲的很多了，这里不再赘述。


通过运行官方示例大家主要了解软件的运行流程就好，熟悉之后可以进行二次开发。


![在这里插入图片描述](https://img-blog.csdnimg.cn/6620200a1915426193f14e4d0b2bc222.png)


### 2. 控制底层+地图采集


用实验车运行Autoware，首先要调通控制底层，底层一般是`CAN`通讯，有pci接口的can或者usb-can，调试相关驱动使得程序能够控制车辆的油门、制动和转向，有这些最基础的功能后就够了。


地图采集有gps轨迹图或者激光点云图，激光建图的话可以遥控或者驾驶车辆绕所在区域开一圈，让激光雷达稳定地扫描周围环境即可，采集完成后，在软件中用`ndt_mapping`模块来建图。


![在这里插入图片描述](https://img-blog.csdnimg.cn/611ce6c3bbbe42c5afa8ed7cc51282cf.png)


### 3. 感知定位


接入激光雷达后，点云图能正常显示，且与上一步建好的点云地图能匹配上，这里主要用到了`ndt_matching`模块。


![在这里插入图片描述](https://img-blog.csdnimg.cn/5806a541f24b49e29ec15583f7d94abb.png)


如果还用到相机、GPS等其他感知定位设备，调通相关驱动即可，另外，还可以加入检测、分割等感知类算法。


### 4. 规划控制


最简单的话可以直接用Autoware的`Waypoint_planner`、`A*`规划模块和`PurePursuit`控制模块，将之前录包的轨迹保存，然后加载这条轨迹，即可实现路径跟踪功能。


![在这里插入图片描述](https://img-blog.csdnimg.cn/ddb06733284c4beebce6c4367fc564ad.png)


### 5. 仿真或实车运行


ROS工具提供了`rosbag`工具，可以很方便地回放数据包，因此，在这些数据包播放时，启动相关节点调试即实现了仿真。仿真的优势就是可以在不依赖硬件的情况下，随时调试自己相关的软件模块。


当然也可以搭配其他仿真软件来使用，如LGSVL和Carla，这是两个常用的仿真软件，与ROS的适配也好一点。


![在这里插入图片描述](https://img-blog.csdnimg.cn/7ee1520a2f3d4668ab44bf7c85002550.png)


最终软件还是要部署到实车上，前面的条件都具备后，将软件部署到车上，你会发现很多在仿真阶段没有的问题，这时候就是一个不断调试的过程了，这个过程也会进一步考验软件的鲁棒性。


![在这里插入图片描述](https://img-blog.csdnimg.cn/3cef739a7a134d0d8cc3b7a30bd2e3cf.png)


除了算法的二次开发外，还可在此基础上基于socket通信做车联网模块、车机模块、座舱模块等等。


### 6. 心得与计划


对自动驾驶相关技术模块有了初步的理解，如建图、定位、感知、规划和运动控制。了解了Autoware的架构和基本组件，包括感知模块（如点云处理、图像处理）、定位模块（如GPS、IMU）、规划模块（如路径规划、速度规划）以及控制模块（如PID控制、车辆动力学建模）等。具体如下：



> 
> 1.掌握了基于NDT的定位建图算法的原理和代码分析，并在仿真和实车中实现；  
>  2.理解了高精地图的概念，Vector Map格式的解析，并掌握了官方高精地图编辑工具（也可用Unity+插件）；  
>  3.掌握基于点云输入的目标检测算法原理及代码分析，包括欧式聚类、形状估计、目标跟踪等；  
>  4.掌握基于轨迹的决策和路径规划算法原理及代码分析，包括A*、OP等；  
>  5.掌握运动控制的算法原理及代码分析，包括PurePursuit和MPC等。
> 
> 
> 


今后可以从软件或算法优化方面学习，如：



> 
> 1.学习机器学习和深度学习基础知识，掌握常用的神经网络结构、损失函数、优化方法等。  
>  2.了解Autoware中使用的感知模块算法，例如点云处理、图像处理、激光雷达数据处理等。这包括滤波、聚类、分割、目标检测、语义分割等算法。  
>  3.学习Autoware中的定位算法，包括GPS/IMU融合、视觉里程计、多传感器融合等。  
>  4.学习Autoware中的路径规划和速度规划算法，包括基于规则的路径规划、全局路径规划、局部路径规划、PID控制、MPC控制等。  
>  5.了解Autoware中的车辆状态估计和参数识别算法，包括车辆动力学建模、轮胎模型、摩擦系数识别等。  
>  6.掌握Autoware中使用的工具和框架，例如ROS、OpenCV、PCL等，以及常见的机器学习框架TensorFlow、PyTorch等。
> 
> 
> 


最后，通过实验和测试来验证软件和算法的性能和功能，并对其进行优化和改进。


以上。





