cmake_minimum_required(VERSION 2.8.3)
project(pointcloud_octomap_updater2)

find_package(catkin REQUIRED COMPONENTS
  roscpp
  rosconsole
  pcl_ros
  pluginlib
  moveit_ros_perception
)
find_package(Boost REQUIRED)

catkin_package(
  INCLUDE_DIRS
    include
)

include_directories(
  include
  ${catkin_INCLUDE_DIRS} 
)

## Declare a cpp library
add_library(
  ${PROJECT_NAME}
  src/pointcloud_octomap_updater2.cpp
  src/plugin_init.cpp
)

target_link_libraries(${PROJECT_NAME} 
  ${catkin_LIBRARIES} 
  ${Boost_LIBRARIES}
)


