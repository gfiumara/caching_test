cmake_minimum_required(VERSION 3.18)

project(test_project)

set(OpenCV_DIR ${CMAKE_INSTALL_PREFIX}/lib/cmake/opencv4)
message(STATUS "OpenCV_DIR is ${OpenCV_DIR}")
file(GLOB_RECURSE listing LIST_DIRECTORIES true "${OpenCV_DIR}/*")
message(STATUS "${listing}")
find_package(OpenCV REQUIRED)

add_executable(test test.cpp)
target_include_directories(test PUBLIC ${OpenCV_INCLUDE_DIRS})
install(TARGETS test)
