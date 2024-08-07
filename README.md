# loam_velodyne_ouster
## loam_velodyne - With Ouster LIDAR

loam_velodyne_ouster is and modified version of [loam_velodyne](https://github.com/laboshinl/loam_velodyne), which uses Ouster LIDAR instead of velodyne.<br>
This code has been fixed by a junior developer, which could cause unexpected problems. (It works fine in my environment at this point.)<br>
If you ask for a pull request in case of a problem, we will actively reflect it.
## How to build with catkin

```
$ cd ~/catkin_ws/src/
$ git clone https://github.com/reason-rock/loam_velodyne_ouster.git
$ cd ~/catkin_ws
$ catkin_make -DCMAKE_BUILD_TYPE=Release 
$ source ~/catkin_ws/devel/setup.bash
```

## Running

```
roslaunch loam_velodyne loam_ouster.launch
```

In second terminal Prepare Data of OS1-32

```
rosbag play YOUR_DATASET_FOLDER/YOUR_BAGFILE
```

## Troubleshooting

### `multiScanRegistration` crashes right after playing bag file

Issues [#71](https://github.com/laboshinl/loam_velodyne/issues/71) and
[#7](https://github.com/laboshinl/loam_velodyne/issues/7) address this
problem. The current known solution is to build the same version of PCL that
you have on your system from source, and set the `CMAKE_PREFIX_PATH`
accordingly so that catkin can find it. See [this
issue](https://github.com/laboshinl/loam_velodyne/issues/71#issuecomment-416024816)
for more details.


---
[Quantifying Aerial LiDAR Accuracy of LOAM for Civil Engineering Applications.](https://ceen.et.byu.edu/sites/default/files/snrprojects/wolfe_derek.pdf) Derek Anthony Wolfe

[ROS & Loam_velodyne](https://ishiguro440.wordpress.com/2016/04/05/%E5%82%99%E5%BF%98%E9%8C%B2%E3%80%80ros-loam_velodyne/) 
