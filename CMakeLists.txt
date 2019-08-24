cmake_minimum_required(VERSION 3.4)
project(DevOps_pipeline_testing)
enable_testing()
include(CTest)
set(CMAKE_CXX_STANDARD 14)

add_subdirectory(tests)
add_subdirectory(source)