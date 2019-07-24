# RCCAR_ROS [![Build Status](https://travis-ci.org/zhangcaocao/RCCAR_ROS.svg?branch=master)](https://travis-ci.org/zhangcaocao/RCCAR_ROS)


![RCCAR](/rc_car.jpg)

适用于1/10 RC Car 的slam与navigation包

大部分fork自[linorobot](https://github.com/linorobot), 然后teensy部分去除了原有的imu程序，用于适配Imu gy85，需要自己制作一个轮子的编码器不然没法工作的！！


制作编码器的话，使用霍尔传感器`A3144EUAE`自己制作一个，然后加个磁环装在电机轴上即可。


全局规划使用的是 Dijkstra 算法（A*算法也问题不大，差不多）。局部规划使用的是[Teb](http://wiki.ros.org/teb_local_planner)

使用方法详见 [linorobot/README.md](linorobot/README.md)，一步一步跟着走就能成功，祝你好运！


最后由衷感谢[linorobot](https://github.com/linorobot)所做的工作！