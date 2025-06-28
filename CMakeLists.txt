# cmake_minimum_required(VERSION 3.29.0)
# project(planning)
# set(CMAKE_CXX_STANDARD 17)

# # 设置运行时可执行文件的输出目录为项目源代码目录下的 bin 文件夹
# set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${PROJECT_SOURCE_DIR}/bin)   #dll和exe都指定到bin目录下


# # 辅助函数，自动查找指定目录下的所有源文件-
# # 找到src下的cpp文件
# aux_source_directory(${PROJECT_SOURCE_DIR}/src SRC_LISTS)

# # 添加一个名为 common 的共享库
# # 并将 src 下的所有cpp文件编译为共享库
# #目标 权限 来源
# add_library(
# common
# SHARED
# ${SRC_LISTS}
# )
# #  common 库依赖头文件，需要连接到 include 目录下
# #目标 权限 来源
# target_include_directories(
# common
# PUBLIC
# ${PROJECT_SOURCE_DIR}/include
# )

# # 添加可执行文件，指定主源文件
# add_executable(planning_main planning_main.cpp)

# # 设置公共头文件路径，使得可执行文件可以使用这些头文件  main.cpp 需要用到process.h
# #目标 权限 来源
# # target_include_directories(planning_main
# # PUBLIC
# # ${PROJECT_SOURCE_DIR}/include
# # )

# # # 链接库，使得可执行文件可以使用 common 库
# # #目标 权限 来源
# #error: linking the executable failed: planning_main.cpp:10: undefined reference to `Process::planProcess()'
# target_link_libraries(planning_main
# PUBLIC
# common
# )


cmake_minimum_required(VERSION 3.29.0)
project(test1)
set(CMAKE_CXX_STANDARD 17)


# 设置运行时可执行文件的输出目录为项目源代码目录下的 bin 文件夹

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${PROJECT_SOURCE_DIR}/bin)

aux_source_directory(${PROJECT_SOURCE_DIR}/src cpp_files)

add_library(cpp_DLL
SHARED
${cpp_files}
)

target_include_directories(cpp_DLL
PUBLIC
${PROJECT_SOURCE_DIR}/include
)

add_executable(test1_main planning_main.cpp)

target_link_libraries(test1_main
PUBLIC
cpp_DLL
)