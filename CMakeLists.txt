cmake_minimum_required(VERSION 3.27)
project(test_external)

set(CMAKE_CXX_STANDARD 20)

add_library(test_external SHARED library.cpp)
