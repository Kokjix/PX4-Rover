# PX4-Rover
```
git clone -b v1.11.2 https://github.com/PX4/PX4-Autopilot.git

```
This repo is used to add our custom models on PX4 simulations.

1- 3131 rover_21 copied to ROMFS/px4fmu_common/init.d-posix
2- rover_21 folder copied to Tools/sitl_gazebo/models/
3- rover_21.world copied to Tools/sitl_gazebo/worlds
4- sitl_target.cmake copied and changed to platforms/posix/cmake/sitl_target.cmake
