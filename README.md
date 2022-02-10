# PX4-Rover
```
git clone https://github.com/PX4/PX4-Autopilot.git

cd ~/PX4-Autopilot/

git checkout v1.11.2
```
This repo is used to add our custom model (Rover with Aruco-Tag) on PX4 simulations.

1- 3131 rover_21 copied to ROMFS/px4fmu_common/init.d-posix

2- rover_21 folder copied to /Tools/sitl_gazebo/models/

3- rover_21.world copied to /Tools/sitl_gazebo/worlds

4- sitl_target.cmake copied and changed to /platforms/posix/cmake/sitl_target.cmake

5- posix_sitl.launch copied to /launch/posix_sitl.launch

For run this: 
```
DONT_RUN=1 make px4_sitl gazebo #for PX4 build
make px4_sitl gazebo_rover_21 #Running simulation with PX4
roslaunch px4 mavros_posix_sitl.launch vehicle:="rover_21" #Running with PX4 ROS Wrapped
```
## Iris Drone Model with Dual Cam 

Note: It is for newer PX4-Autopilot version. Front and down camera added using .sdf files.

1- fpv_cam_up AND iris_fpv_cam folders copiad and changed to /Tools/sitl_gazebo/models

2- In /launch/posix_sitl.launch change .sdf file path to "<arg name="sdf" default="$(find mavlink_sitl_gazebo)/models/iris_fpv_cam/iris_fpv_cam.sdf"/>"
```
DONT_RUN=1 make px4_sitl gazebo
roslaunch px4 mavros_posix_sitl.launch
```

## Marsyard with ARTags Environment
```
git clone --recurse-submodules https://github.com/itu-rover/Simulations.git
```
1- Clone "blender_gazebo" and "marsyard" packages into the ros workspace which contains mavros and mavlink packages.

2- Dowload git lfs and follow the instructions in https://drive.google.com/file/d/1v8TXeXEdQh3YSndxKcN7ITRKnqt_aL_D/view?usp=sharing 

3- Edit "blender_gazebo/sdf/landmark.sdf.xacro" file according to your file path

For run this:
```
roslaunch px4 posix_sitl.launch
```
DON'T FORGET START SIMULATION (bottom left start button) WHEN GAZEBO LAUNCHED
