<img src="https://raw.githubusercontent.com/linorobot/lino_docs/master/imgs/wiki/logo1.png" width="200" height="200" />

# linorobot [![Build Status](https://travis-ci.org/linorobot/lino_install.svg?branch=master)](https://travis-ci.org/linorobot/lino_install)
Linorobot is a suite of Open Source ROS compatible robots that aims to provide students, developers, and researchers a low-cost platform in creating new exciting applications on top of ROS.

## Tutorial

You can read the full tutorial how to build your robot [here](https://github.com/grassjelly/linorobot/wiki/1.-Getting-Started).

#### Uploading the codes:
```
cd ~/linorobot_ws/src/linorobot/teensy/firmware
platformio run --target upload
```

## Creating a Map
![alt text](https://github.com/linorobot/lino_docs/blob/master/imgs/readme/slam.png?raw=true)

#### Launch base driver:
```
roslaunch linorobot bringup.launch
```

#### Launch mapping packages:
```
roslaunch linorobot slam.launch
```

## Autonomous Navigation
[![IMAGE ALT TEXT](http://img.youtube.com/vi/aqzMq-jMd-c/maxresdefault.jpg)](https://www.youtube.com/embed/aqzMq-jMd-c "Linorobot Autonomous Navigation")

#### Launch base driver:
```
roslaunch linorobot bringup.launch
```

#### Launch navigation packages:
```
roslaunch linorobot navigate.launch
```
