cmake_minimum_required(VERSION 3.27)
project(test_external)

set(CMAKE_CXX_STANDARD 20)

add_library(test_external SHARED src/library.cpp)
target_include_directories(test_external PUBLIC include)

find_package(OpenCV CONFIG REQUIRED)
# note: 13 additional targets are not displayed.
target_link_libraries(test_external PRIVATE opencv_ml tegra_hal opencv_dnn opencv_core)


# Specify the installation directory for the library
install(TARGETS test_external
        LIBRARY DESTINATION lib
        ARCHIVE DESTINATION lib)

# Specify the installation directory for header files
install(DIRECTORY include/
        DESTINATION include)