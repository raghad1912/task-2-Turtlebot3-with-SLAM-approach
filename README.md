# task-2-Turtlebot3-with-SLAM-approach

###  Use Turtlebot3 with SLAM approach to create and save a map


#### the steps that take to do this task : 

 * install ubountu and ROS 
 * install all dependencies required 
 * install turtlebot3 packages
 * set a default turtlebot3 model name 
 * install turtlebot3 simulation packages
 * Launch Simulation World
 * run SLAM node
 * save map


#### this link will help you to do this task [turtlebot3](https://emanual.robotis.com/docs/en/platform/turtlebot3/overview/)

#### <h2>step 1: install a ubountu and ROS </h2>
#### first install ubountu and then ROS 
#### <h2>step 2: install all dependencies we need  </h2>

<p><code>$ sudo apt-get install ros-melodic-joy ros-melodic-teleop-twist-joy \
  ros-melodic-teleop-twist-keyboard ros-melodic-laser-proc \
  ros-melodic-rgbd-launch ros-melodic-depthimage-to-laserscan \
  ros-melodic-rosserial-arduino ros-melodic-rosserial-python \
  ros-melodic-rosserial-server ros-melodic-rosserial-client \
  ros-melodic-rosserial-msgs ros-melodic-amcl ros-melodic-map-server \
  ros-melodic-move-base ros-melodic-urdf ros-melodic-xacro \
  ros-melodic-compressed-image-transport ros-melodic-rqt* \
  ros-melodic-gmapping ros-melodic-navigation ros-melodic-interactive-markers
</code></p>

![task2installdependency](https://user-images.githubusercontent.com/56357074/123694935-a0bbf800-d862-11eb-81af-5ac8cce810ea.png)

#### <h2>step 3: install turtlebot3 packages  </h2>


<p><code>$ sudo apt-get install ros-melodic-dynamixel-sdk</code></p>

<p><code>$ sudo apt-get install ros-melodic-turtlebot3-msgs</code></p>

<p><code>$ sudo apt-get install ros-melodic-turtlebot3</code></p>


<h2>step 4: set a default TurtleBot3 Model Name</h2>

<p><code>$ echo "export TURTLEBOT3_MODEL=waffle_pi" >> ~/.bashrc</code></p>

<h2>step 5:  install a turtlebot3 simulation package</h2>

<p><code>cd ~/catkin_ws/src/
</code></p>

<p><code>$ git clone -b melodic-devel https://github.com/ROBOTIS-GIT/turtlebot3_simulations.git
</code></p>


<p><code>$ cd ~/catkin_ws && catkin_make</code></p>


#### <h2>step 6: launch simulation world </h2>
- by choosing one of simulation enviroment, but if you want create map with SLAM so choose either 
     TurtleBot3 World or TurtleBot3 House. 
    
- i will choose TurtleBot3 World :

<p><code>$ export TURTLEBOT3_MODEL=waffle
</code></p>
<p><code>$ roslaunch turtlebot3_gazebo turtlebot3_world.launch
</code></p>

![task2turtlrbot3world](https://user-images.githubusercontent.com/56357074/123694909-9a2d8080-d862-11eb-9d3f-8ab828f12ba7.png)


- to make a turtlebot 3 mode operate with keyboard , use this command : 

<p><code>$ roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch
</code></p>

https://user-images.githubusercontent.com/56357074/123695021-b9c4a900-d862-11eb-9347-e6471bece710.mp4


#### <h2>step 7: run SLAM node </h2>


<p><code>$ export TURTLEBOT3_MODEL=waffle
</code></p>

<p><code>$ roslaunch turtlebot3_slam turtlebot3_slam.launch slam_methods:=gmapping
</code></p>

![task2RunSLAMwithoutUsingKeyboard](https://user-images.githubusercontent.com/56357074/123694959-a6194280-d862-11eb-88e7-22c90aa28c32.png)

- to run a teleoperation :

<p><code>$ export TURTLEBOT3_MODEL=burger</code></p>

<p><code>$ roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch</code></p>

https://user-images.githubusercontent.com/56357074/123694994-b29d9b00-d862-11eb-911a-03c2c9e75145.mp4


#### <h2>step 8: save map  </h2>

<p><code>$ rosrun map_server map_saver -f ~/map</code></p>





























