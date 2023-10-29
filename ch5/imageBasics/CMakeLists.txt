cmake_minimum_required(VERSION 3.0)

project(imageBasics)

# 设置可执行文件的名称和源文件
add_executable(imageBasics imageBasics.cpp)
add_executable(undistortImage undistortImage.cpp)

# 查找并加载OpenCV，设置OpenCV_INCLUDE_DIRS、OpenCV_LIBRARIES等变量
find_package(OpenCV REQUIRED)
# 设置头文件路径（如果需要的话）
include_directories(${OpenCV_INCLUDE_DIRS})
# 链接OpenCV库到可执行文件，让可执行文件能够使用Pangolin库的功能
target_link_libraries(imageBasics ${OpenCV_LIBRARIES})
target_link_libraries(undistortImage ${OpenCV_LIBRARIES})
