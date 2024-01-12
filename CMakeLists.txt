cmake_minimum_required(VERSION 3.27)
project(test_external)

set(CMAKE_CXX_STANDARD 20)

add_library(test_external SHARED src/library.cpp)
target_include_directories(test_external PUBLIC include)

# Specify the installation directory for the library
install(TARGETS test_external
        LIBRARY DESTINATION lib
        ARCHIVE DESTINATION lib)

# Specify the installation directory for header files
install(DIRECTORY include/
        DESTINATION include)