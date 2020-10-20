# fetchRobotRecycle
Here is the Group project for Robotics Assignment 2. For Fetch Robot Recycling 

## Important information:
The following package builds on top of the fetch gazebo ros package. 
Please install al fetch robot packages from ROS

## Spawn Model
In order to get  all the models to gazebo please copy all the folders that are inside the model file.  Paste it in the following location

~~~~bash
/home/.gazebo/models
~~~~
## Person Tracking Dependencies. 
Please add the following folders into your catkin workspace. These file are under People_tracking_depencies
~~~bash
humanoid_msgs
pal_msgs
catkin_make
~~~
To add install external depencies please run 
~~~
sudo apt-get install ros-melodic-kalman-filter 
sudo apt-get install ros-melodic-easy-markers 
sudo apt-get install ros-melodic-face-detector
~~~
alternatively, to install all dependencies please run
~~~bash
rosdep install --from-paths src --ignore-src -r -y
~~~


Add the human detection package into your workspace
~~~bash
pal_person_detector_opencv
catkin_make
~~~
Note: this package was mapped to an Intel RealSense D435i. If you want to use another camera. Please edit the topic or remap the topic from the launch file 

~~~
roslaunch pal_person_detector_opencv detector.launch
~~~
To visualise the detection please run 
~~~
rosrun image_view image_view image:=/person_detector/debug
~~~

## Human Detection Mode Notes
If you dont have a camera device such as a Intel realsense. Please run the rosbags. 
These bags are in the correspoding folder.
To run the bags. Open Terminal
~~~
- roscore
- rosbag play <NAME OF BAG> -l
~~~