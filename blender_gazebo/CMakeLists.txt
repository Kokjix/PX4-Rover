cmake_minimum_required(VERSION 2.8.3)
project(blender_gazebo)

find_package(catkin REQUIRED COMPONENTS
  xacro
)

catkin_package()
include_directories(
  ${catkin_INCLUDE_DIRS}
)

#Need to generate .world file from .xacro file.
file(GLOB xacro_files worlds/*.world.xacro)
xacro_add_files(${xacro_files} TARGET generate_world_files)

install(DIRECTORY blender_gazebo worlds
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)

install(PROGRAMS scripts/install
  DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
)

#this need to artag texture
install(DIRECTORY
  media
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)

#this need to genereta marsyard2021.world file
install(DIRECTORY worlds
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
  PATTERN "*.world"
)
