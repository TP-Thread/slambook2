cmake_minimum_required(VERSION 2.8)
project(EXAMPLES)

# include_directories("/usr/include/eigen3")
# add_executable(coordinateTransform coordinateTransform.cpp)

# 查找名为Pangolin的库，并指定它是项目的必需依赖项
# 当CMake在CMakeLists.txt文件中遇到这行代码时，将在系统上搜索Pangolin。如果找到Pangolin并且已安装，CMake将配置项目以使用它
find_package(Pangolin REQUIRED)
# Pangolin_INCLUDE_DIRS、Pangolin_LIBRARIES 是由 find_package(Pangolin) 命令设置的变量
# 包含Pangolin库的头文件路径
include_directories(${Pangolin_INCLUDE_DIRS})
add_executable(plotTrajectory plotTrajectory.cpp)
# 将 Pangolin_LIBRARIES 中包含的库链接到 plotTrajectory 目标中，以使 plotTrajectory 能够使用Pangolin库的功能
target_link_libraries(plotTrajectory ${Pangolin_LIBRARIES})
