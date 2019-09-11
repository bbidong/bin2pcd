cmake_minimum_required(VERSION 2.6) 
project(view_pcd) 
find_package(PCL 1.2 REQUIRED) 
include_directories(${PCL_INCLUDE_DIRS}) 
link_directories(${PCL_LIBRARY_DIRS}) 
add_definitions(${PCL_DEFINITIONS}) 
add_executable(view_pcd view_pcd.cpp) 
target_link_libraries (view_pcd ${PCL_LIBRARIES}) 

