# 声明要求的 cmake 最低版本
cmake_minimum_required( VERSION 2.8 )

# 声明一个 cmake 工程
project( test_icp )

set(CMAKE_BUILD_TYPE "Release")
set(CMAKE_CXX_FLAGS "-std=c++11")
set(CMAKE_CXX_FLAGS_RELEASE "-O3 -Wall -g")

find_package(PCL REQUIRED)

include_directories(${PCL_INCLUDE_DIRS})

link_directories(${PCL_LIBRARY_DIRS})

# 设置编译模式
# set( CMAKE_BUILD_TYPE "Debug" )

# 添加一个可执行程序
add_executable( icp_main icp_main.cpp )
target_link_libraries(icp_main ${PCL_LIBRARIES})

add_executable( icp_score icp_score.cpp )
target_link_libraries(icp_score ${PCL_LIBRARIES})

add_executable( ndt_main ndt_main.cpp )
target_link_libraries(ndt_main ${PCL_LIBRARIES})