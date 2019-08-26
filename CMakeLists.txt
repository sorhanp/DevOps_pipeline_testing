cmake_minimum_required(VERSION 3.4)
set(CMAKE_CXX_STANDARD 14)
project(DevOps_pipeline_testing)

include(CTest)
enable_testing()

add_subdirectory(source)
add_subdirectory(tests)
