cmake_minimum_required(VERSION 3.18)

project(test_project)

find_package(OpenCV REQUIRED HINTS ${CMAKE_INSTALL_PREFIX}/lib/cmake)

add_executable(test test.cpp)
target_include_directories(test PUBLIC ${OpenCV_INCLUDE_DIRS})
install(TARGETS test)
