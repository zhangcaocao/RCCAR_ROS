/ teensy / firmware 

小车的底层控制代码，主要实现的是电机的速度PID闭环控制;Imu（Gy85）数据读取并且发布;解析“cmd_vel”的指令，利用相关运动学的知识计算出舵机转向的角度与电机的速度; 发布里程计消息。

各个函数的作用：

```
void PIDCallback(const lino_msgs::PID& pid)
```
更新PID参数。

```
void commandCallback(const geometry_msgs::Twist& cmd_msg)
```
保存速度指令


```
void moveBase()
```
在 `void loop()`中循环执行， 频率为 COMMAND_RATE， 首先是根据指令计算需要给各个电机的转速`kinematics.getRPM`，然后根据编码器获取电机的真实转速`motor1_encoder.getRPM();`，之后利用PID计算需要添加到电机的占空比`spin(motor1_pid.compute(req_rpm.motor1, current_rpm1));`，然后再计算需要的转向角，作用到舵机上。获取当前的真实速度，然后发布到`/raw_vel`，`raw_vel_pub.publish(&raw_vel_msg);`。

```
void stopBase()
```

    //this block stops the motor when no command is received
        if ((millis() - g_prev_command_time) >= 400)
    {

        stopBase();
    }



```
void publishIMU()
```
发布IMU的数据，发布到 `raw_imu`， `raw_imu_pub.publish(&raw_imu_msg);`。
