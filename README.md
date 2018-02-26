## Overview
This is the sorce cod for ARIAC(http://gazebosim.org/ariac) qualifier1 (qual1a and qual1b). More details about the qualifier1
can be find at: https://bitbucket.org/osrf/ariac/wiki/2017/qualifiers/qual1. The tasks are completed by controlling the arm following
a hard-code trajector. For each order, a grasping and placing motion is programmed with two points: middle and goal point. The arm will
move to those two points respectively in order to avoid the obstacles and do its task(grasping or placing parts).

## TO DO
We are moveing to an other way to control the arm: MoveIt! It will be easier for us to control the arm without worrying about the path
planning.

## Pre-required
- Ubuntu 16.04
- ROS
- ARIAC

## Install and Build
In your workspace/src folder, do:
```
git clone https://github.com/zzjkf2009/ARIAC_Qual1a.git
cd ..
catkin_make
source devel/setup.bash
```

## Run:
### For **qual1a**:
From *Terminal*:
```
rosrun osrf_gear gear.py -f `catkin_find --share osrf_gear`/config/qual1a.yaml $(rospack find qual1)/config/team_conf.yaml
rosrun qual1 qual1_node
```
### For **qual1b**
From *Terminal*:
```
rosrun osrf_gear gear.py -f `catkin_find --share osrf_gear`/config/qual1b.yaml $(rospack find qual1)/config/team_conf.yaml
rosrun qual1 qual1b_node
```

## Result:
log files are stored in folder "ariac_qual1_log" and the simulation can be reviewed by playback the log with the code:
```
roslaunch osrf_gear gear_playback.launch
```
Or if you want to specify a specific log file:
```
roslaunch osrf_gear gear_playback.launch state_log_path:=`pwd`/ariac_qual1_log/qual1/qual1a/gazebo/state.log
