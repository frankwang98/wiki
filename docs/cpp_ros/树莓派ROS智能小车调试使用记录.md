最近手里有一辆 clb 的树莓派ROS履带小车，不过放了好久，功能有点问题，最近打算把小车重新拆装、清洗，软件也重新刷写，然后顺便记录以下功能调试的过程。

### 一、简介


记得以前大家玩智能小车基本是以STM32为主控，搭配摄像头、超声波雷达等传感器，但随着自动驾驶开始热起来后，大家都开始用树莓派、ROS系统、激光雷达这些部件来组装一辆智能小车了。


或许是教育方面的引导，一辆智能小车就类似于自动驾驶的原型系统，STM32下位机是汽车ECU的缩影，而树莓派/Jetson是自动驾驶车辆计算平台的缩影，学习激光雷达感知、摄像头感知，路径规划，下位机通讯与执行等功能。


### 二、机械部分


拆散后的履带小车车架如图所示：


![在这里插入图片描述](https://img-blog.csdnimg.cn/6d8ab9f0e1aa45cea2b560b84858b3f5.jpeg)


背面（包含电池、电机）：


![在这里插入图片描述](https://img-blog.csdnimg.cn/90bbdf9dc1d84677975ab5c98edd362a.jpeg)


车架整体图如下（由6部分零件组成）：


![在这里插入图片描述](https://img-blog.csdnimg.cn/570cf4a2530a415289a4cd21b8b787bc.jpeg)


组装好的车架如下：


![在这里插入图片描述](https://img-blog.csdnimg.cn/7d029e1da7f243678716ec97fa2020b5.jpeg)


### 三、电气部分


安装STM32驱动板，接上电源和电机。


### 四、软件部分


树莓派安装Ubuntu Mate系统，然后安装ROS：


![在这里插入图片描述](https://img-blog.csdnimg.cn/e5cb0ffe31a94c58b3ca51484561f797.png)


安装ssh，使得可以远程调试：



```bash
sudo apt-get install openssh-server
sudo systemctl start ssh
sudo systemctl enable ssh

```

### 五、功能调试


* 控制底盘运动
* 激光雷达测试及SLAM
* 相机测试及物体检测
* 路径规划与运动控制


这个博主有详细记录功能调试过程：[创乐博机器人调试](http://t.csdn.cn/Yd87G)


以上。





