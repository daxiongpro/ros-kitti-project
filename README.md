## ROS1(melodic) + python2.7 + Pycharm

### 1.Install ROS and miniconda3

### 2.Create conda virtual environment

`conda create -n ros1_py27 python=2.7`

### 3.Create ROS work_space

```bash
mkdir ~/catkin_ws && cd catkin_ws
mkdir src && cd src
git clone https://github.com/daxiongpro/ros-kitti-project.git  # catkin_create_pkg ros-kitti-project
cd ../../   # catkin_ws
catkin_init_workspace
catkin_make
```

### 4.Make pycharm configration

* [Add ros dist-package in your environment](https://blog.csdn.net/weixin_38405166/article/details/114808500).
* Set up Environment Variable in Pycharm[libcv_bridge.so](https://blog.csdn.net/qq_42800654/article/details/123553599),[tf2_ros](https://blog.csdn.net/weixin_44445507/article/details/118335039), it is for the same purpose of `source devel/setup.zsh` in Pycharm.

### 5.Prepare kitti dataset

* Download kitti raw dataset`2011_09_26_calib.zip` and `2011_09_26_drive_0005_sync.zip`
* Generate dataset directory as follows:

```bash
kitti_raw_data
├── 2011_09_26
│   ├── 2011_09_26_drive_0005_sync
│   │   ├── image_00
│   │   ├── image_01
│   │   ├── image_02
│   │   ├── image_03
│   │   ├── oxts
│   │   └── velodyne_points
│   ├── calib_cam_to_cam.txt
│   ├── calib_imu_to_velo.txt
│   └── calib_velo_to_cam.txt
├── 2011_09_26_calib.zip
└── 2011_09_26_drive_0005_sync.zip
```

### 6.Run python script

* Change the dataset path in python script
* Run python:
  eg:`python showkitti.py`(in ros-kitti-project/v1-publish-pointcloud)

### 7.RVIZ visualization

* Run rviz

```bash
roscore
rviz
```

* Add Pointcloud topic

---

Now, you can see the pointcloud published!
