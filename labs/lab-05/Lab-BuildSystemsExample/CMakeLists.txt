cmake_minimum_required(VERSION 3.10)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED True)

# set the project name and version
project(lab5 VERSION 1.0)

add_executable(lab5 program.c)

add_subdirectory(source)
add_subdirectory(headers)
