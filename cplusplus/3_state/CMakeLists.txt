# 作者  ： JohnnyWang
# log   :   
#=======2017.08.16.16:35(星期三)======= 创建文件

cmake_minimum_required(VERSION 2.8)
#工程名
PROJECT (state_pattern)
#设置全局变量
set (EXTRA_LIBS ${EXTRA_LIBS} state context)
#注意，如果一个库要引用其他库的函数，需要将被引用的库放在后面
find_package (Threads)
#添加库文件
add_library(state     SHARED src/state.cpp)
add_library(context   SHARED src/context.cpp)
#添加可执行文件
add_executable(state_pattern src/main.cpp)
#链接
target_link_libraries(state_pattern ${EXTRA_LIBS} ${CMAKE_THREAD_LIBS_INIT})
