# VINS-Mono
## A Robust and Versatile Monocular Visual-Inertial State Estimator


## 1. Prerequisites
1.1 **Ubuntu** and **ROS**
Ubuntu  16.04.
ROS Kinetic. [ROS Installation](http://wiki.ros.org/ROS/Installation)
additional ROS pacakge
```
    sudo apt-get install ros-YOUR_DISTRO-cv-bridge ros-YOUR_DISTRO-tf ros-YOUR_DISTRO-message-filters ros-YOUR_DISTRO-image-transport
```


1.2. **Ceres Solver**
Follow [Ceres Installation](http://ceres-solver.org/installation.html), remember to **make install**.
(Our testing environment: Ubuntu 16.04, ROS Kinetic, OpenCV 3.3.1, Eigen 3.3.3) 

## 2. Build VINS-Mono on ROS
Clone the repository and catkin_make:
```
    cd ~/catkin_ws/src
    git clone https://github.com/HKUST-Aerial-Robotics/VINS-Mono.git
    cd ../
    catkin_make
    source ~/catkin_ws/devel/setup.bash
```
## 3. Run (Modified part by HuynhDucMinh)
Run the tracking package (choose 1 depend on what simulation program you use)
```
    roslaunch vins_estimator euroc.launch config_file:=airsim.yaml
    roslaunch vins_estimator euroc.launch config_file:=flightmare.yaml
    roslaunch vins_estimator euroc.launch config_file:=flightgoogles.yaml
    roslaunch vins_estimator euroc.launch config_file:=default.yaml
```

Run the Rviz visualization node:
```
    roslaunch vins_estimator vins_rviz.launch 
```


## 3. Visual-Inertial Odometry and Pose Graph Reuse on Public datasets
Download [EuRoC MAV Dataset](http://projects.asl.ethz.ch/datasets/doku.php?id=kmavvisualinertialdatasets). Although it contains stereo cameras, we only use one camera. The system also works with [ETH-asl cla dataset](http://robotics.ethz.ch/~asl-datasets/maplab/multi_session_mapping_CLA/bags/). We take EuRoC as the example.



## 8. Licence
The source code is released under [GPLv3](http://www.gnu.org/licenses/) license.

We are still working on improving the code reliability. For any technical issues, please contact Tong QIN <tong.qinATconnect.ust.hk> or Peiliang LI <pliapATconnect.ust.hk>.

For commercial inquiries, please contact Shaojie SHEN <eeshaojieATust.hk>

**Related Papers**

* **Online Temporal Calibration for Monocular Visual-Inertial Systems**, Tong Qin, Shaojie Shen, IEEE/RSJ International Conference on Intelligent Robots and Systems (IROS, 2018), **best student paper award** [pdf](https://ieeexplore.ieee.org/abstract/document/8593603)

* **VINS-Mono: A Robust and Versatile Monocular Visual-Inertial State Estimator**, Tong Qin, Peiliang Li, Zhenfei Yang, Shaojie Shen, IEEE Transactions on Robotics[pdf](https://ieeexplore.ieee.org/document/8421746/?arnumber=8421746&source=authoralert) 

*If you use VINS-Mono for your academic research, please cite at least one of our related papers.*[bib](https://github.com/HKUST-Aerial-Robotics/VINS-Mono/blob/master/support_files/paper_bib.txt)
