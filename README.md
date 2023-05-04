

##### 1.Git Clone
```
cd catkin_ws/srcc
git clone https://github.com/JensenZhaoUT/ur5_grasping_gazebo.git
cd ..
catkin_make
source devel/setup.bash
```

#### 2. Test
```
roslaunch ur5_single_arm_tufts ur5_single_arm_gazebo.launch
rosrun ur5_single_arm_manipulation grasping_demo_vision2.py
```
#### 3. Simulation
##### start simulation environment
```
roslaunch ur5_single_arm_tufts ur5_single_arm_gazebo.launch
```
##### recognize the poses of the objects and post to the TF tree
```
roslaunch find_object_2d find_object_3d_kinect2.launch
```
##### subscribe the existing pose and send it to the robotic arm
```
rosrun opencv tf_listener.py
```
##### proceed the grasping operation with the grasp estimation to grasp the object
```
rosrun ur5_single_arm_manipulation grasping_demo_vision2.py
```

#### 4 Potential Issues

##### 4.1 Gripper85 Issue
Use this to replace robotiq_85_gripper if there is an issue
```
git clone https://github.com/artursg/robotiq_85_gripper.git
```

##### 4.2 Cmake error(control_toolbox)
Error: Could not find a package configuration file provided by "control_toolbox"
```
sudo apt-get install ros-indigo-control-toolbox
```

reference：
```
https://github.com/Dzy-HW-XD/kinectv2_ur5
https://github.com/harrycomeon/ur5-gazebo-grasping.git
```










 
