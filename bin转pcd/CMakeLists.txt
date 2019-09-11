cmake_minimum_required(VERSION 2.8.3)
project(kitti_velodyne) 
 
add_compile_options(-std=c++11)
 
 
find_package(catkin REQUIRED COMPONENTS
pcl_ros
roscpp
)
 
find_package(PCL 1.7 REQUIRED)
 
catkin_package(
  INCLUDE_DIRS include
  CATKIN_DEPENDS roscpp pcl_ros
)
 
include_directories(
 include
 ${catkin_INCLUDE_DIRS}
)
link_directories(${PCL_LIBRARY_DIRS})
 
add_executable(bin2pcd bin2pcd.cpp)   
 
 
 
target_link_libraries(bin2pcd
  ${catkin_LIBRARIES}
  ${PCL_LIBRARIES}
)
