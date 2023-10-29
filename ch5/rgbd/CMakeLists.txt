cmake_minimum_required(VERSION 3.0)
project(stereoVision)
# 设置可执行文件的名称和源文件
add_executable(joinMap joinMap.cpp)

# 查找并加载库
find_package(OpenCV REQUIRED)
find_package(Sophus REQUIRED)
find_package(Pangolin REQUIRED)

# 设置头文件路径
include_directories(${OpenCV_INCLUDE_DIRS})
include_directories(${Sophus_INCLUDE_DIRS})
include_directories(${Pangolin_INCLUDE_DIRS})

# 链接库到可执行文件
target_link_libraries(joinMap Sophus::Sophus ${OpenCV_LIBRARIES} ${Pangolin_LIBRARIES})