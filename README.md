# PX4-Rover
```
git clone https://github.com/PX4/PX4-Autopilot.git

cd ~/PX4-Autopilot/

git checkout v1.11.2
```
This repo is used to add our custom models on PX4 simulations.

1- 3131 rover_21 copied to ROMFS/px4fmu_common/init.d-posix

2- rover_21 folder copied to Tools/sitl_gazebo/models/

3- rover_21.world copied to Tools/sitl_gazebo/worlds

4- sitl_target.cmake copied and changed to platforms/posix/cmake/sitl_target.cmake

## marsyard

For marsyard you should clone `blender_gazebo` and `marsyard` texture into the ros workspace which contains mavros and mavlink package and change sdf path to according to this README https://github.com/Kokjix/Simulations.git

marsyard: [https://github.com/itu-rover/Simulations.git](https://github.com/itu-rover/Simulations.git)
blender_gazebo: [https://github.com/Kokjix/blender_gazebo.git](https://github.com/Kokjix/blender_gazebo.git)
