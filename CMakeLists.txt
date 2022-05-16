cmake_minimum_required (VERSION 3.8)

#项目名称
project(demo)
set(PROJECT_DEMO demo)

#使用c++17标准
set(CMAKE_CXX_STANDARD 17)

#引入头文件
include_directories(
        ${CMAKE_CURRENT_SOURCE_DIR}/app
)

#引入源文件
file(GLOB SRC_LIST "app/*.cpp")

#生成可执行文件
add_executable(${PROJECT_DEMO} ${SRC_LIST})

#链接静态库和动态库
target_link_libraries(
        ${PROJECT_DEMO}
        -Wl,--start-group
        pthread
        -Wl,--end-group
)
